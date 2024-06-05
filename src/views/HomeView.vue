<template>
  <!-- Fruits Shop Start-->
  <div class="container-fluid fruite py-1">
    <div class="container py-1">
      <div class="tab-class text-center">
        <div class=" ">
          <div class="col-lg-12 " v-if = "categoriaNombre != null">
            
            <h1> Productos de la categoría <strong>{{ categoriaNombre }} </strong></h1>
            <a
                  class="btn btn-primary rounded-pill m-1 mb-5"
                  style="width: 300px"
                  href="#"
                  role="button"
                  @click="resetFilter"
            >Ver todos los productos
            </a>
            <div class="alert alert-danger" role="alert" v-if="productosFiltrados.length === 0 "  >
              No existen productos en esta categoría!
            </div>
          </div>
          <div class="col-lg-12 " v-if = "categoriaNombre === null">
            <h1>Nuestros Productos</h1>
            <ul class="nav nav-pills d-inline-flex text-center mb-5">
              <li class="nav-item">
                <a
                  name=""
                  id=""
                  class="btn btn-primary rounded-pill m-1"
                  style="width: 130px"
                  href="#"
                  role="button"
                  v-for="cat in categorias"
                  :key="cat.id"
                  @click="getCategoriaID(cat.id, cat.nombre)"
                  >{{ cat.nombre }}</a
                >
              </li>
            </ul>
          </div>
        </div>
        <div class="container">
          
            <div class="row g-4" >
              <div class="col-lg-12">
                <div class="row g-4" > 
                  <div class="col-md-6 col-lg-4 col-xl-3"  v-for="prod in productosFiltrados"
                  :key="prod.id">
                    <div class="rounded position-relative fruite-item"  >
                      <div class="fruite-img" >
                        <img
                          :src=" prod.imagen "
                          class="img-fluid w-100 rounded-top"
                          alt=""
                          style="height: 15rem;"
                        />
                      </div>
                      <div
                        class="text-white bg-primary px-3 py-1 rounded position-absolute"
                        style="top: 10px; left: 10px"
                      >
                        {{ prod.categoria_nombre }}
                      </div>
                      <div
                        class="p-4 border border-secondary border-top-0 rounded-bottom" 
                      >
                        <h4> {{ prod.nombre}} </h4> 
                        <p style="height: 5rem;">
                          {{ prod.descripcion }}
                        </p>
                        <div
                          class="d-flex justify-content-center flex-lg-wrap"
                        >
                          <p class="text-dark fs-5 fw-bold mb-0">$ {{ prod.precio }} / {{ prod.precio_tipo_descripcion }} </p>
                          
                        </div>
                      </div>
                    </div>
                  </div>
                  
                </div>
              </div>
            </div>

        </div>
      </div>
    </div>
  </div>
  <!-- Fruits Shop End-->
</template>

<script>
import axios from "axios";

export default {
  name: "HomeView",

  data() {
    return {
      categorias: [],
      productos: [],
      productosFiltrados: [],
      categoriaNombre: null,
    };
  },

  methods: {
    getCategoriaID(categoriaID, categoriaNombre) {
      this.categoriaNombre = categoriaNombre;
      if (categoriaID) {
        this.productosFiltrados = this.allProductos.filter((prod) => prod.categoria === categoriaID);
      } else {
        this.productosFiltrados = this.allProductos
      }
    },

    resetFilter() {
      this.categoriaNombre = null
      this.productosFiltrados = this.allProductos
    }


  },

  mounted() {
    axios
      .get("http://127.0.0.1:8000/api/categoria/")
      .then((response) => (this.categorias = response.data))
      .catch((error) => console.log(error));
    
    axios
      .get("http://127.0.0.1:8000/api/productos/")
      .then(response => {
        this.allProductos = response.data
        this.productosFiltrados = this.allProductos
      })
      .catch((error) => console.log(error));
  },
};
</script>
