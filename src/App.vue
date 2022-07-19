<template>
  <div id="app">
    <div>
      <div class="np-credits">wwww.nightprogrammer.com</div>
      <img
        :src="$options.imgUrl"
        :class="{
          'img-default-size': true,
          'img-elevated-size': imageElevated,
        }"
        @mouseover="floatImage"
        @mouseout="shrinkImage"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "ImageFloat",
  created() {
    this.$options.imgUrl =
      "https://images.unsplash.com/photo-1480796927426-f609979314bd";
  },
  data() {
    return {
      imageElevated: false,
    };
  },
  methods: {
    shrinkImage() {
      this.imageElevated = false;
    },
    floatImage() {
      this.imageElevated = true;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}
.img-default-size {
  height: 200px;
  transition: all 0.3s;
}

.img-elevated-size {
  height: 250px;
  transition: all 0.3s;
  box-shadow: 6px 6px 20px rgb(66, 66, 66);
  transform: rotate(-3deg);
}

.np-credits {
  font-size: 12px;
  margin-bottom: 12px;
  color: #4b4b4b;
}
</style>