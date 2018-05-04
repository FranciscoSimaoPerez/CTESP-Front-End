<template>
  <div>
    <The-header @sideNavToggle="displaySideNav = !displaySidenav" />
    <TheSideNav :show="displaySideNav" @close="displaySideNav=false" />
    <main class="main-content">
      <nuxt/>
    </main>
  </div>
</template>

<script>
  //import navbar from "~/components/navbar.vue"
  import TheHeader from '@/components/TheHeader/TheHeader.vue';
  import TheSideNav from "@/components/TheSideNav/TheSideNav.vue";

  export default {
    components: {
      TheHeader,
      TheSideNav
    },
    data() {
      return{
        displaySideNav: false
      }
    },
  }
</script>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    font-family: "Lato", sans-serif;
  }

  .main-content {
    margin-top: 4.5rem;
  }
</style>