<template>
    <div class="owl-carousel owl-theme" v-carousel>
        <slot></slot>
    </div>
</template>
<script>
import "owl.carousel";

export default {
  name: "VOwlCarousel",
  props: {
    items: {
      default: 3
    },
    margin: {
      default: 0
    },
    loop: {
      default: false
    },
    center: {
      default: false
    },
    nav: {
      default: true
    },
    autoplay: {
      default: false
    },
    autoplaySpeed: {
      default: false
    },
    rewind: {
      default: true
    },
    mouseDrag: {
      default: true
    },
    touchDrag: {
      default: true
    },
    pullDrag: {
      default: true
    },
    freeDrag: {
      default: false
    },
    stagePadding: {
      default: 0
    },
    autoWidth: {
      default: false
    },
    autoHeight: {
      default: false
    },
    dots: {
      default: true
    },
    autoplayTimeout: {
      default: 5000
    },
    autoplayHoverPause: {
      default: false
    }
  },

  data() {
    return {
      items: this.items,
      margin: this.margin,
      loop: this.loop,
      center: this.center,
      nav: this.nav,
      autoplay: this.autoplay,
      autoplaySpeed: this.autoplaySpeed,
      rewind: this.rewind,
      mouseDrag: this.mouseDrag,
      touchDrag: this.touchDrag,
      pullDrag: this.pullDrag,
      freeDrag: this.freeDrag,
      stagePadding: this.stagePadding,
      autoWidth: this.autoWidth,
      autoHeight: this.autoHeight,
      dots: this.dots,
      autoplayTimeout: this.autoplayTimeout,
      autoplayHoverPause: this.autoplayHoverPause
    };
  },

  directives: {
    carousel: {
      inserted(el) {
        $(el)
          .owlCarousel(this.data())
          .trigger();
        console.log("carousel Started");
      }
    }
  }
};
</script>
<style scoped>
@import "owl.carousel/dist/assets/owl.theme.default.css";
@import "owl.carousel/dist/assets/owl.carousel.css";
</style>
