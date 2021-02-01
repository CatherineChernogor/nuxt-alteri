<template>
  <div class="idea">
    <div class="heading button-head">
      <span class>НАША ИДЕОЛОГИЯ</span>
    </div>

    <div class="slider mask clr-mono1 quote">
      <span class="bclr-mono3 quote-border prev">{{ list[next - 1] }}</span>
      <span class="bclr-mono3 quote-border cur">{{ list[cur - 1] }}</span>
      <span class="bclr-mono3 quote-border next">{{ list[prev - 1] }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      list: [
        "new experience",
        "breaking boundaries between the worlds",
        "стремимся к невозможному",
      ],
      next: 3,
      cur: 2,
      prev: 1,
    };
  },

  methods: {
    showGalliry() {
      setInterval(() => {
        this.moveSlide();
      }, 10000);
    },
    moveSlide() {
      this.cur = this.eval(this.cur + 1);
      this.next = this.eval(this.next + 1);
      this.prev = this.eval(this.prev + 1);
    },
    eval(ind) {
      if (ind > this.list.length) ind -= this.list.length;
      return ind;
    },
  },
  mounted() {
    this.showGalliry();
  },
};
</script>

<style lang="scss" scoped>
@import "/assets/css/vars";
.idea {
  opacity: inherit;
}
.button-head.heading {
  padding: 20px 30px;
  span {
 
    border: solid $mono3 2px;
    padding: 10px 20px;
  }
}

.slider {
  opacity: inherit;
  overflow: visible;
  position: relative;
  width: 100%;
  height: inherit/2;
  .quote-border {
    padding: 3px 5px;
  }
}

.mask {
  overflow: hidden;
  height: 320px;
  @include flexible;
}

.slider ul {
  margin: 0;
  padding: 0;
  position: relative;
}

.prev,
.next {
  display: none;
}
</style>