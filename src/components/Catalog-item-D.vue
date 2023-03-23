<template>
  <div class="card">
    <article class="card__article">
      <div class="card__top">
        <div class="card__hot">
          Хит продаж
          <img src="@/assets/icons/fire.png" alt="">
        </div>
        <img
          class="card__img"
          :src="require('@/assets/icons/' + product_data.image)"
          alt="img"
        >
        <div class="card__sell">
          {{ product_data.sell }}
        </div>
      </div>
      <div class="card__dottom">
        <div class="card__content">
          <p class="card__brend">{{ product_data.brend }}</p>
          <p class="card__desc">{{ product_data.desc }}</p>
          <div class="card__price">
            <span class="card__price-new">{{ product_data.price }} Р.</span>
            <span class="card__price-last">{{ product_data.price }} Р.</span>
          </div>
        </div>
        <div v-if="product_data.available">
          <button class="card__btn border-blue" @click="addToCart">купить</button>
        </div>
        <div v-else><button class="card__btn-grey border-grey" @click="addToCart">Сообщить о поступлении</button></div>
      </div>
    </article>
  </div>
</template>

<script>
export default {
  name: 'catalog-card',
  components: {},
  props: {
    product_data: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  data () {
    return {
    }
  },
  methods: {
    addToCart () {}
  }
}
</script>

<style lang="scss">
.card {
  cursor: pointer;
  flex-basis: 22%;
  margin: 12px;
}
.card__top {
  position: relative;
  width: 100%;
  height: 200px;
  background: #F8F8FA;
}
.card__img {
  padding-top: 60px;
  display: block;
  margin: auto;
  transition: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  &:hover {
    zoom: 1.2;
  }
}
.card__hot {
  position: absolute;
  margin: 12px ;
  padding: 8px;
  background: #fff;
  border: 1px solid #F2F2F2;
  border-radius: 4px;
}
.card__sell {
  position: absolute;
  left: 12px;
  bottom: 12px;
  padding: 8px;
  background: #7397F5;
  color: #fff;
  border: 1px solid #F2F2F2;
  border-radius: 4px;
}
.card__dottom {
  margin: 16px 16px 16px 0;
}
.card__brend {
  color: #AAAAAA;
  margin-bottom: 8px;
}
.card__desc {
  margin-bottom: 16px;
  &:hover {
    color: #7397F5;
  }
}
.card__price {
  font-weight: 700;
  font-size: 16px;
  margin-bottom: 16px;
}
.card__price-new {
  margin-right: 10px;
}
.card__price-last {
  font-weight: 400;
  font-size: 12px;
  text-decoration: line-through;
  color: #AAAAAA;
}
.card__btn {
  text-transform: capitalize;
  font-weight: 700;
  padding: 16px 12px;
  background: none;
  color: #7397F5;
  &:hover {
    color: #000;
    background: #7398f588;
  }
}
.card__btn-grey {
  white-space: nowrap;
  width: 100%;
  text-transform: capitalize;
  font-weight: 700;
  padding: 16px 12px;
  background: none;
  color: #AAAAAA;
  &:hover {
    color: #000;
    background: #AAAAAA88;
  }
}
@media(max-width: 1441px) {
  .card__btn-grey {
    white-space: normal;
    padding: 10px 12px;
  }
}
@media(max-width: 800px) {
  .card {
    cursor: pointer;
    flex-basis: 45%;
    margin: 0px;
  }
}
</style>
