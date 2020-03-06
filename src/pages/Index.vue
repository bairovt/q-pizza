<template>
  <q-page ref="index_page">
    <!-- <img alt="Quasar logo" src="~assets/quasar-logo-full.svg"> -->
    <div class="q-pa-md">
      <q-carousel
        animated
        v-model="slide"
        navigation
        infinite
        autoplay
        transition-prev="slide-right"
        transition-next="slide-left"
        :height="carouselHeight"
      >
        <q-carousel-slide :name="'g1'" img-src="statics/images/slider/Aldo_Apachi_slider.jpg" />
        <q-carousel-slide :name="'b2'" img-src="statics/images/slider/Amerika2_slider.jpg" />
        <q-carousel-slide :name="'n3'" img-src="statics/images/slider/Ranch_slider.jpg" />
      </q-carousel>
    </div>
  </q-page>
</template>

<script>
import { dom } from "quasar";
const { style } = dom;

export default {
  name: "PageIndex",
  data() {
    return {
      slide: "g1",
      carouselHeight: "100px"
    };
  },
  computed: {},
  mounted() {
    this.setCarouselHeight();
  },
  methods: {
    setCarouselHeight() {
      const width = this.$refs.index_page.$el.clientWidth;
      this.carouselHeight = (width - 16 * 2) / 3.44 + "px"; // 16xp - 2 paddings, slide image width & height ratio
    }
  }
};
</script>
