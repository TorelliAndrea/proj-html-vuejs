<script>
export default {
   name: "PageHeader",
   data() {
      return {
         count: 0
      }
   },
   props: {
      headerNav: Array,
   }
}
</script>

<template>
   <div class="container d-flex justify-content-around p-3 align-items-center fixed-top">
      <div class="cp">
         <img src="/img/logo-2.png" alt="Logo Softbox">
      </div>
      <nav class="navbar navbar-expand-lg bg-body-tertiary">
         <div class="container-fluid">
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
               aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
               <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavDropdown">
               <ul class="navbar-nav" v-for="link in headerNav">
                  <li class="nav-item"><a class="py-2 mx-2 text-decoration-none" :href="'#' + link">{{ link }}</a></li>
               </ul>
               <div class="icons px-4 fw-bolder">
                  <i class="fa-solid fa-magnifying-glass p-3 cp fs-5"></i>
                  <i class="fa-solid fa-cart-shopping p-3 cp fs-5 position-relative" @click="count++">
                     <span class="position-absolute top-5 start-98 translate-middle badge rounded-pill bg-primary">
                        {{ this.count }}
                     </span>
                  </i>
               </div>
               <div class="my-btn">Get Started</div>
            </div>
         </div>
      </nav>
   </div>
</template>

<style lang="scss" scoped>
@use '../styles/variables.scss' as *;

.container {
   background-color: $primo-bg;
}

img {
   height: 3rem;
}

a {
   color: $ottavo-text;
   border-bottom: solid 2px $primo-border;
   transition: all 0.2s;

   &:hover {
      color: $quinto-text;
      border-bottom: solid 2px $terzo-border;
   }
}

.my-header {
   position: fixed;
   top: 0;
   left: 0;
}

.badge {
   font-size: 0.6rem;
}
</style>