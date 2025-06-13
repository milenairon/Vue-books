<template>
    <header class="header">
        <div class="header__container container">
            <a href="/" class="header__logo link">
                <img src="../assets/images/icons/logo.svg" alt="Книги для олимпийцев" class="header__logo-icon" uk-svg />
            </a>

            <button class="header__burger" @click="toggleMenu" :class="{ 'menu-open': isOpen }">
                <img src="../assets/images/icons/header-arrow.svg" alt="Стрелка" class="header__burger-icon" uk-svg />
            </button>

            <a href="#" class="header__basket link">
                 <span v-if="countBook" class="header__count-book text text_m color-accent">{{ countBook }}</span>
                <img src="../assets/images/icons/header-basket.svg" alt="Корзина" class="header__basket-icon" uk-svg />
            </a>
        </div>

        <div class="menu-overlay" :class="{ 'menu-open': isOpen }" @click="closeMenu"></div>

        <div id="header__burger-menu" class="header__burger-menu" :class="{ 'menu-open': isOpen }">
             <nav class="header__burger-menu-content">
                <ul class="header__burger-menu-items">
                    <li class="header__burger-menu-item"><a class="header__burger-menu-link link link_accent text text_m" href="/">Главная</a></li>
                    <li class="header__burger-menu-item"><a class="header__burger-menu-link link link_accent text text_m" href="/">Каталог</a></li>
                    <li class="header__burger-menu-item"><a class="header__burger-menu-link link link_accent text text_m" href="/">Корзина</a></li>
                </ul>
            </nav>
        </div>
    </header>
</template>


<script>
export default {
  data() {
    return {
      isOpen: false,
      isModalOpen: false,
      countBook: this.getCountBook()
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
    closeMenu() {
      this.isOpen = false;
    },
    getCountBook() {
      const cart = JSON.parse(localStorage.getItem('cart'));
      return cart ? cart.length : 0;
    }
  },
};
</script>