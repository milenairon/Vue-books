<template>
  <section class="form">
    <div class="form__container container">
      <h2 class="form__title text text_l">Хотите знать о книгах всё?</h2>
      <p class="form__subtitle text">Подпишитесь на нашу новостную рассылку</p>
      <form class="form__form" @submit.prevent="handleSubmit" novalidate>
        <div class="form__box">
        <input
          type="email"
          class="form__input"
          placeholder="Ваш email"
          v-model="email"
          :class="{ 'input-error': emailError }"
        />
        <button type="submit" class="form__button btn" :disabled="isSubmitting">
          {{ isSubmitting ? "Отправка..." : "Отправить" }}
        </button>
        </div>
        <span v-if="emailError" class="form__error-message error-message">{{ emailError }}</span>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      emailError: null,
      isSubmitting: false,
    };
  },
  methods: {
    validateEmail() {
      if (!this.email) {
        this.emailError = "Пожалуйста, введите email";
        return false;
      }

      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailRegex.test(this.email)) {
        this.emailError = "Пожалуйста, введите корректный email";
        return false;
      } else {
        this.emailError = null;
        return true;
      }      
    },
    async handleSubmit() {
      if (!this.validateEmail()) {
        return;
      }

      this.isSubmitting = true;
      try {
        // Дальнейшие улучшения кода: отправка данных на сервер (fetch или axios)
        console.log("Отправка email:", this.email);

        // Имитация отправки данных
        await new Promise((resolve) => setTimeout(resolve, 1000));

        alert("Спасибо за подписку!");
        this.email = "";
      } catch (error) {
        console.error("Ошибка при отправке:", error);
        alert("Произошла ошибка при отправке. Попробуйте, пожалуйста, позже.");
      } finally {
        this.isSubmitting = false;
      }
    },
  },
};
</script>