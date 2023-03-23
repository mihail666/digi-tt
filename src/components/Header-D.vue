<template>
  <div class="header">
    <div class="header__container flex">
      <span class="customHoverBlack"> <span />
        <div class="header__logo flex">
          <img src="@/assets/icons/logo.png" alt="">
          <p class="header__logo-text" >
            Логотип
          </p>
        </div>
      </span>
      <div class="header__btn">
        <p class="btn border-blue">
          Каталог
        </p>
      </div>
      <div class="search">
        <form action="">
          <input
            class="search__input border-blue"
            type="text"
            placeholder="Поиск по 100 000 товаров"
          >
          <i class="search__icon">
            <img src="@/assets/icons/search.png" alt="">
          </i>
        </form>
      </div>
      <div class="search-375px">
        <form action="">
          <div class="flex">
            <i class="search-375px__icon">
              <img src="@/assets/icons/searchM375.png" alt="">
            </i>
            <div class="search-375px__border">
              <input
                class="search-375px__input"
                type="text"
                placeholder="Запрос"
              >
              <button class="search-375px__btn-reset">+</button>
              <button
                class="search-375px__btn-search"
                type="submit"
              >
                найти
              </button>
            </div>
          </div>
        </form>
        <div class="search-375px__title">
          Название категории
        </div>
      </div>
        <ul class="header__items flex">
          <li
            class="header__item"
            v-for="(menu, index) in headerMenuList"
            :key="index"
          >
            <router-link
              class="header__link"
              aria-current="page"
              :to="menu.path"
            >
            <span class="customHoverBlack"> <span />
              {{ menu.name }}
            </span>
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { menuList } from '@/const/menuLinks'
export default {
  data () {
    return { headerMenuList: menuList }
  }
}
</script>

<style lang="scss">
.header {
  height: 72px;
  margin: 0 auto;
  &__container {
    padding-top: 12px;
    box-sizing: border-box;
  }
  &__item {
    padding-left: 10px;
    white-space: nowrap;
  }
  &__logo {
    margin:0 15px;
  }
  &__logo-text {
    margin-left: 10px;
  }
}
.search {
    position: relative;
    width: 1000px;
    min-width: 240px;
  &__input {
    width: 100%;
    padding: 12px 0px 12px 48px;
    box-sizing: border-box;
    display: flex;
    align-items: flex-start;
    cursor: pointer;
  }
  &__icon {
    position: absolute;
    top: 12px;
    left: 12px;
  }
}
.search-375px {
  display: none;
  position: relative;
  width: 375px;
  height: 43px;
  &__border {
    position: relative;
    border-bottom: 1px solid #D5D5D5;
  }
  &__input {
    width: 180px;
    padding: 12px 0px;
    margin: 0 6px 6px 6px;
    border-radius: 5px;
    border: none;
  }
  &__btn-search {
    padding: 12px 16px;
    background: #7397F5;
    border-radius: 5px;
    border: none;
  }
  &__btn-reset {
    position: absolute;
    top: 4px;
    right: 80px;
    width: 30px;
    height: 30px;
    font-size: 25px;
    font-weight: 700;
    border-radius: 50%;
    rotate: 45deg;
    border: none;
  }
  &__title{
    color: #333333;
    font-weight: 400;
    font-size: 22px;
    line-height: 28px;
  }
}
</style>
