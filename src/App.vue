<script>
import Slider from "./components/Slider.vue";
import img1 from "./assets/images/img1.jpg";
import img2 from "./assets/images/img2.jpg";
import img3 from "./assets/images/img3.jpg";
import img4 from "./assets/images/img4.jpg";
import img5 from "./assets/images/img5.jpg";
import img6 from "./assets/images/img6.jpg";
import img7 from "./assets/images/img7.jpg";
import img8 from "./assets/images/img8.jpg";
import img9 from "./assets/images/img9.jpg";
import img10 from "./assets/images/img10.jpg";

export default {
  components: {
    Slider,
  },
  data() {
    return {
      imagesList: [img1, img2, img3, img4, img5, img6, img7, img8, img9, img10],
    };
  },
};
</script>


<template>
  <main>
    <Slider :images="imagesList" />
  </main>
</template>
