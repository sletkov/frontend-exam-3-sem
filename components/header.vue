<template>
  <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
          <div class="container-fluid">
              <a class="navbar-brand" href="#">Sletkov</a>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarSupportedContent">
                  <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                      <li class="nav-item">
                          <NuxtLink class="nav-link" to="/">Главная</NuxtLink>
                      </li>
                      <li class="nav-item">
                          <NuxtLink class="nav-link" to="about">О нас</NuxtLink>
                      </li>
                      <li class="nav-item">
                          <NuxtLink class="nav-link" to="animals">Животные</NuxtLink>
                      </li>
                  </ul>
              </div>
          </div>
      </nav>
  </header>
</template>

<script>
export default {
  name: "headerComponent"
}
</script>

<style scoped>
</style>
