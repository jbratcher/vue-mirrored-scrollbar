<template>
  <div class="scrollbar" :style="style">
    <div class="scrollbar-thumb"></div>
  </div>
</template>

<script>
export default {
  name: "VirtualScroll",
  props: {
    target: {
      type: String,
      default: ""
    },
    height: {
      type: String,
      default: ""
    },
    width: {
      type: String,
      default: ""
    }
  },
  computed: {
    style() {
      return `height: ${this.height}; width: ${this.width}; top: ${this.targetElementOffset.y}px`;
    }
  },
  data() {
    return {
      targetElement: {},
      targetElementOffset: {}
    };
  },
  methods: {
    getTargetElementById(id) {
      console.log(document.getElementById(id));
      this.targetElement = document.getElementById(id);
    },
    scrollbarThumbPosition() {
      // thumb is 5% of scrollbar height
      if (this.targetElement) {
        const scrollbarThumb = document.querySelector(".scrollbar-thumb");
        this.targetElement.addEventListener("scroll", event => {
          console.log("Scroll top: " + this.targetElement.scrollTop);
          console.log("Client height: " + this.targetElement.scrollHeight);
          console.log(
            "Scroll position: " +
              String(
                (
                  (this.targetElement.scrollTop /
                    this.targetElement.scrollHeight) *
                  100 *
                  3.92
                ).toFixed(0) + "%"
              )
          );
          var scrollPosition = String(
            (
              (this.targetElement.scrollTop / this.targetElement.scrollHeight) *
              100 *
              3.92
            ).toFixed(0) + "%"
          );
          var scrollPositionValue = Number(scrollPosition.replace("%", ""));
          if (scrollPositionValue >= 95) {
            scrollbarThumb.style.top = "auto";
            scrollbarThumb.style.bottom = 0;
          } else {
            scrollbarThumb.style.top = String(
              (
                (this.targetElement.scrollTop /
                  this.targetElement.scrollHeight) *
                100 *
                3.92
              ).toFixed(0) + "%"
            );
          }
        });
      }
    }
  },
  mounted() {
    this.getTargetElementById(this.target);
    if (this.targetElement) {
      this.targetElementOffset = this.targetElement.getBoundingClientRect();
      this.scrollbarThumbPosition();
    }
  }
};
</script>

<style lang="scss">
.scrollbar {
  background: none;
  border: 0.125rem solid teal;
  height: 20rem;
  width: 0.5rem;
  position: absolute;
  .scrollbar-thumb {
    background: teal;
    height: 1rem;
    position: absolute;
    width: 0.33rem;
  }
}
</style>
