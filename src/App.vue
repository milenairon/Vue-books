<template>
   <appHeader/>

  <main>
    <Banner />
    <Slider />
    <Description />
   <appForm/>
  </main>

   <appFooter/>
</template>


<script>
import Header from './components/Header.vue';
import Banner from './components/Banner.vue';
import Slider from './components/Slider.vue';
import Description from './components/Description.vue';
import Form from './components/Form.vue';
import Footer from './components/Footer.vue';

export default {
    components: {
      appHeader: Header,
      Banner,
      Slider,
      Description,
      appForm: Form,
      appFooter: Footer,
    },
}
</script>

