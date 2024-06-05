<template>

<!-- Navbar start -->
        
    <nav class="navbar navbar-light bg-white navbar-expand-xl">
        <a href="index.html" class="navbar-brand"><h1 class="text-primary display-6">Verdulería</h1></a>
        <button class="navbar-toggler py-2 px-3" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
            <span class="fa fa-bars text-primary"></span>
        </button>
        <div class="collapse navbar-collapse bg-white" id="navbarCollapse">
            <div class="navbar-nav mx-auto">
            <router-link to="/" class="nav-item nav-link">Home</router-link> 
            <router-link to="/about" class="nav-item nav-link">Contacto</router-link>
                
            </div>
            <div class="d-flex m-3 me-0">
            <form class="d-flex" role="search">
                <input class="form-control me-2" type="search" placeholder="Buscar ..." aria-label="Search">
                <button class="btn btn-outline-primary" type="submit">Buscar</button>
            </form>
                
            </div>
        </div>
        
    </nav>
    <hr>

  <!-- Navbar End -->


</template>

<script>
export default {
  name: 'NavbarComponents',
  
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped >

</style>
