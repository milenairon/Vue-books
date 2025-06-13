<template>
    <section class="slider">
        <div class="slider__container container">
            <h2 class="slider__title">Горячие новинки</h2>

            <div class="slider__wrapper">
                <div class="slider__slide" v-for="(book, index) in books"
                :key="index"
                :class="{ 'active': currentIndex === index }"
                :style="{ transform: `translateX(calc(-100% * ${currentIndex} - 20px * ${currentIndex}))` }"
                >

                    <div class="slider__slide-container">
                        <img :src="book.image" :alt="book.title" class="slider__slide-image" />
                        <h3 class="slider__slide-title text">{{ book.author }}. "{{ book.title }}"</h3>
                    </div>
                    <div class="slider__slide-container">
                        <p class="slider__slide-genre text text_s">{{ book.genre }}</p>
                        <div class="slider__slide-box">
                            <span class="slider__slide-price text text_m">{{ book.price }} р.</span>
                            <button class="slider__slide-btn btn" @click="addToCart(book)" type="button">Купить</button>
                        </div>
                    </div>

                </div>                
            </div>

            <div class="slider__navigation">
                <button class="slider__nav-btn slider__nav-btn_prev" @click="prevSlide" :disabled="isFirstSlide">
                    <img src="/src/assets/images/icons/slider-arrow.svg" alt="Стрелка" class="slider__nav-btn-icon" uk-svg />
                </button>

                <div class="slider__dots">
                    <span
                    v-for="(book, index) in books"
                    :key="index"
                    class="slider__dot"
                    :class="{ 'active': currentIndex === index }"
                    @click="goToSlide(index)"
                    ></span>
                </div>

                <button class="slider__nav-btn slider__nav-btn_next" @click="nextSlide" :disabled="isLastSlide">
                    <img src="/src/assets/images/icons/slider-arrow.svg" alt="Стрелка" class="slider__nav-btn-icon" uk-svg />
                </button>
                  

            </div>
        </div>
    </section>
</template>



<script>
export default {
  data() {
    return {
      books: [
        {
          image: '/src/assets/images/content/slider-vern.png',
          author: 'Ж. Верн',
          title: 'Двадцать тысяч лье под водой',
          genre: 'Приключения',
          price: 168,
        },
        {
          image: '/src/assets/images/content/slider-kun.png',
          author: 'Н. Кун',
          title: 'Легенды и мифы Древней Греции',
          genre: 'Эпос и фольклор',
          price: 174,
        },
        {
          image: '/src/assets/images/content/slider-gomer.png',
          author: 'Гомер',
          title: 'Илиада',
          genre: 'Эпос и фольклор',
          price: 155,
        },
        {
          image: '/src/assets/images/content/slider-vern.png',
          author: 'Ж. Верн',
          title: 'Двадцать тысяч лье под водой',
          genre: 'Приключения',
          price: 168,
        },
        {
          image: '/src/assets/images/content/slider-vern.png',
          author: 'Ж. Верн',
          title: 'Двадцать тысяч лье под водой',
          genre: 'Приключения',
          price: 168,
        },
      ],
      currentIndex: 0,
      cart: [],
    };
  },
  mounted() {
    this.loadCartFromLocalStorage();
  },
  computed: {
    isFirstSlide() {
      return this.currentIndex === 0;
    },
    isLastSlide() {
      return this.currentIndex === this.books.length - 1;
    },
  },
  methods: {
    nextSlide() {
      if (!this.isLastSlide) {
        this.currentIndex++;
        
      }
    },
    prevSlide() {
      if (!this.isFirstSlide) {
        this.currentIndex--;
      }
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
    addToCart(book) {
      this.cart.push(book);
      console.log('Корзина:', this.cart.length);
      this.saveCartToLocalStorage();
    },    
    saveCartToLocalStorage() {
      localStorage.setItem('cart', JSON.stringify(this.cart));
      
    },
    loadCartFromLocalStorage() {
      const cartString = localStorage.getItem('cart');
      if (cartString) {
        try {
          this.cart = JSON.parse(cartString);
        } catch (error) {
          console.error('Ошибка при разборе JSON из localStorage:', error);
          this.cart = []; // Сброс корзины в случае ошибки
        }
      }
    },
  },
};
</script>



