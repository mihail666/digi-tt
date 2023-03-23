<template>
  <div class="home">
    <div class="row">
      <div class="col">
        <div class="sidebar">
          <div class="row">
            <category-filter :categories="categoriesArr" />
          </div>
          <div class="row">
            <price-filter :price="pricesArr" />
          </div>
          <div class="row">
            <brand-filter :brand="bransArr" />
          </div>
          <div class="row">
            <size-filter :size="sizeArr" />
          </div>
        </div>
      </div>
      <div class="col">
        <catalog-d :products="products_Arr" />
      </div>
    </div>
  </div>
</template>

<script>
import CategoryFilter from '@/components/filters/Category-filter.vue'
import PriceFilter from '@/components/filters/Price-filter.vue'
import BrandFilter from '@/components/filters/Brand-filter.vue'
import SizeFilter from '@/components/filters/Size-filter.vue'
import CatalogD from '@/components/Catalog-D.vue'
import { productsArr } from '@/const/products'
export default {
  components: {
    CatalogD,
    CategoryFilter,
    PriceFilter,
    BrandFilter,
    SizeFilter
  },
  data () {
    return {
      products_Arr: productsArr
    }
  },
  computed: {
    categoriesArr () {
      return this.products_Arr.map(p => p.category)
    },
    pricesArr () {
      return this.products_Arr.map(p => p.price)
    },
    bransArr () {
      return this.products_Arr.map(p => p.brand)
    },
    sizeArr () {
      return this.products_Arr.map(p => p.size)
    }
  }
}
</script>
<style>
.sidebar {
  width: 280px;
}
</style>
