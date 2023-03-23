<template>
  <div class="prise filter">
    <h2 class="side-title title-center">Цена</h2>
    <form
      class="flex"
      action=""
    >
      <input
        type="numder"
        class="side-input"
        id="n1"
        placeholder="от 5500"
        v-model.number="n1"
      > -
      <input
        type="numder"
        class="side-input"
        id="n2"
        placeholder="до 5500"
        v-model.number="n2"
      >
    </form>
  </div>
</template>

<script>

export default {
  props: {
    price: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  data: () => ({
    n1: '',
    n2: ''
  })
}
</script>
