<template>
  <div class="category filter">
      <h2 class="category-filter__title side-title">Категории</h2>
    <div class="list">
      <div
        class="list-elem"
        v-for="c in categories"
        :key="c.id"
        @click="choosecCat"
      >
        <div>{{ c }}</div>
        <div>{{ categories.length }}</div>
      </div>
      <label></label>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    categories: {
      type: Object,
      default () {
        return {}
      }
    }
  }
}
</script>
