<template>
<nav class="navbar navbar-expand-lg navbar-light">
  <div class="container-fluid">
    <RouterLink to="/" class="navbar-brand">Electro</RouterLink>
    <button
      class="navbar-toggler"
      type="button"
      data-mdb-toggle="collapse"
      data-mdb-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <i class="fas fa-bars"></i>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
            <RouterLink to="/" class="nav-link active">Home</RouterLink>
        </li>
        <li class="nav-item">
            <RouterLink to="/gallery" class="nav-link">Products</RouterLink>
        </li>
        <li class="nav-item">
            <RouterLink to="/about" class="nav-link">About</RouterLink>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<style>
nav{
  background-color:white ;
}
</style>