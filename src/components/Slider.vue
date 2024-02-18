<script>
import next_icon from "../assets/icons/next.png";

export default {
  props: ["images"],
  data() {
    return {
      currentIndex: 0,
      nextIcon: next_icon,
    };
  },
  computed: {
    currentImg() {
      return this.images[this.currentIndex];
    },
  },
  methods: {
    nextImg() {
      this.currentIndex = this.currentIndex === this.images.length - 1 ? 0 : this.currentIndex + 1;
    },
    prevImg() {
      this.currentIndex = this.currentIndex === 0 ? this.images.length - 1 : this.currentIndex - 1;
    },
    showImg(index) {
      if (index < this.images.length && index >= 0) {
        this.currentIndex = index;
      }
    },
  },
};
</script>


<template>
  <div class="slider">
    <div class="current-slide">
      <button class="prev" @click="prevImg">
        <img :src="nextIcon" alt="" class="button-img">
      </button>
      <div class="current-slide--img">
        <img :src="currentImg" alt="currentImg" />
      </div>
      <button class="next" @click="nextImg">
        <img :src="nextIcon" alt="" class="button-img">
      </button>
    </div>
    <div class="controls">
      <button
        v-for="(image, index) in images"
        key="index"
        @click="showImg(index)"
        :class="{ active: index === currentIndex }"
        class="slide-button"
      >{{ index + 1 }}</button>
    </div>
  </div>
</template>


<style scoped>
button {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.slider {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 980px;
}

.current-slide {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
  margin-bottom: 30px;
}

.current-slide--img {
  display: flex;
  justify-content: center;
  height: 700px;
  width: 500px;
  overflow: hidden;
}

.current-slide--img > img {
  object-fit: cover;
}

.prev, .next {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 100px;
  background: transparent;
  border: none;
}

.prev:hover, .next:hover {
  background-color:aqua;
}

.prev > img {
  transform: rotate(180deg);
}

.button-img {
  height: 100%;
}

.controls {
  display: flex;
  gap: 7px;
}

.slide-button {
  background: transparent;
  border: 3px solid black;
  color:black;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  font-size: 20px;
}

.slide-button.active {
  background-color: aqua;
}
</style>
