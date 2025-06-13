<template>
  <section className="description">
    <div className="description__container container">

      <div className="description__cell description__cell_with_image" :style="imageStyleBooks"></div>

      <div className="description__cell description__cell_with_text">
        <h2 className="description__cell-title color-accent">О нас</h2>
        <p className="description__cell-text color-accent">Книжное наследие от мыслителей Древней Греции и до людей современности. Это не просто магазин, а настоящий клуб любителей книги, который объединяет в своем культурном пространстве людей самых разных интересов.</p>
      </div>

      <div className="description__cell description__cell_with_text">
        <h2 className="description__cell-title color-accent">Гармония</h2>
        <p className="description__cell-text color-accent">Наш проект «Гармония» объединяет читателей и авторов в реальности и в интернете. Каждую неделю проводятся встречи онлайн и вживую. Из наших регулярных рубрик вы узнаете много нового о книгах и писателях.</p>
      </div>

      <div className="description__cell description__cell_with_image" :style="imageStyleStatue"></div>

    </div>
  </section>
</template>

<script>
import imageBooks from '../assets/images/background/description-books.jpg';
import imageStatue from '../assets/images/background/description-statue.jpg';

export default {
  data() {
    return {
      imageStyleBooks: {
        backgroundImage: `url(${imageBooks})`,
      },
      imageStyleStatue: {
        backgroundImage: `url(${imageStatue})`,
      },
    };
  },
};
</script>