<template>
  <div class="slideshow">
    <div class="slideshow__buttons">
      <button @click="previousImage" class="slideshow__button">&lt;</button>
      <button @click="nextImage" class="slideshow__button">&gt;</button>
    </div>

    <div class="slideshow__slides">
      <figure class="slideshow__slide">
        <img
          class="slideshow__img"
          :src="currentSlide.file"
          :alt="currentSlide.title"
        />
        <figcaption class="slideshow__caption">
          {{ currentSlide.caption }}
        </figcaption>
      </figure>
    </div>

    <div class="slideshow__dots">
      <button
        class="slideshow__dot"
        @click="goToIndex(index)"
        v-for="(slide, index) in slides"
        :aria-label="`Go to image ${index + 1}`"
      ></button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
      slides: [
        { title: "Interior", caption: "Interior", file: "assets/interior.jpg" },
        { title: "Bike", caption: "Bike", file: "assets/bike.jpg" },
        { title: "Carlo", caption: "Carlo", file: "assets/carlo.jpg" },
      ],
    };
  },
  computed: {
    currentSlide() {
      return this.slides[this.index];
    },
  },

  methods: {
    previousImage() {
      this.index = this.index === 0 ? this.slides.length - 1 : this.index - 1;
    },

    nextImage() {
      this.index = this.index === this.slides.length - 1 ? 0 : this.index + 1;
    },

    goToIndex(index) {
      this.index = index;
    },
  },
};
</script>

<style>
.slideshow {
  position: relative;
  width: 40vw;
  height: 50vh;
}

.slideshow:hover .slideshow__caption {
  opacity: 1;
}

.slideshow__slides {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: pink;
}

.slideshow_slide {
  position: absolute;
  width: 100%;
  height: 100%;
}

.slideshow__img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.slideshow__caption {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  text-align: center;
  font-size: 0.75em;
  padding: 0.5em;
  background: brown;
  opacity: 0;
}

.slideshow__buttons {
  position: absolute;
  top: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  z-index: 10;
  display: flex;
  justify-content: space-between;
}

.slideshow__button {
  padding: 0.5em;
  text-transform: uppercase;
  color: black;
  background: white;
}

.slideshow__dots {
  position: absolute;
  bottom: 0;
  transform: translateY(100%);
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  padding: 0.5em;
  width: 100%;
}

.slideshow__dot {
  min-width: 1em;
  min-height: 1em;
  display: block;
  border-radius: 100%;
  margin-left: 10px;
}
</style>