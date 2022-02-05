<template>
  <footer>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
          <div class="container-fluid">
              <a class="navbar-brand" href="#">Sletkov 201-321 05.02.2022</a>
<!--                  <ul class="navbar-nav me-auto mb-2 mb-lg-0">-->
<!--                      <li class="nav-item">-->
<!--                          <NuxtLink class="nav-link" to="/">Главная</NuxtLink>-->
<!--                      </li>-->
<!--                      <li class="nav-item">-->
<!--                          <NuxtLink class="nav-link" to="About">О нас</NuxtLink>-->
<!--                      </li>-->
<!--                      <li class="nav-item">-->
<!--                          <NuxtLink class="nav-link" to="animals">Животные</NuxtLink>-->
<!--                      </li>-->
<!--                  </ul>-->
          </div>
      </nav>
  </footer>
</template>

<script>
export default {
  name: "footerComponent"
}
</script>

<style scoped>
    footer {
        position: absolute;
        bottom:0;
        left:0;
        width: 100%;
    }
</style>
