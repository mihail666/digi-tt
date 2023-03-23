<template>
  <div class="container">
    <header-d />
    <router-view />
  </div>
</template>

<script>
import HeaderD from './components/Header-D.vue'
export default {
  components: {
    HeaderD
  }
}
</script>
