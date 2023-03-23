<template>
  <div class="catalog">
    <div class="catalog__list">
      <catalog-item-d v-for="p in products" :key="p.article" :product_data="p"
        @addToCart.prevent="" />
    </div>
  </div>
</template>

<script>
import CatalogItemD from '@/components/Catalog-item-D.vue'
export default {
  name: 'catalog-d',
  components: {
    CatalogItemD
  },
  props: {
    products: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  computed: {},
  methods: {},
  mounted () {}
}
</script>

<style lang="scss">
.catalog {
  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
}
</style>
