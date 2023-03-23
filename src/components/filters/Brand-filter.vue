<template>
  <div class="brand filter">
    <div class="flex side-title">
      <h2 class="">Бренд</h2>
      <p class="brand-filter__btn">Очистить</p>
    </div>
    <div class="side-search">
      <form action="">
        <input
          class="side-search__content"
          type="text"
          placeholder="Поиск"
        >
        <div class="side-search__icon">
          <img src="@/assets/icons/search.png" alt="">
        </div>
      </form>
    </div>
    <div class="list">
      <div
        class="list-elem"
        v-for="b in brand"
        :key="b.id"
      >
        <input
          id="brand"
          class="custom-checkbox"
          name="brand"
          type="radio"
          value="b"
        >
        <label for="brand">{{ b }}</label>
        <div>{{ brand.length }}</div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    brand: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  data: () => ({
    selectBran: ''
  })
}
</script>
