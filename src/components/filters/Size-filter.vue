<template>
  <div class="filter">
    <h2 class="side-title title-center">Размер</h2>
    <div class="list">
      <div
        class="list-elem"
        v-for="s in size"
        :key="s.id"
      >
        <input
          id="size"
          class="custom-checkbox"
          name="size"
          type="radio"
          value="s"
        >
        <label for="size">{{ s }}</label>
        <div>{{ size.length }}</div>
      </div>
    </div>
  </div>
</template>
<script>

export default {
  props: {
    size: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  data: () => ({
    selectSize: ''
  })
}
</script>
