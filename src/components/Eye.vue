<template>
  <div class="eye">
    <div class="box">
      <div class="is-flex is-justify-content-space-between is-flex-wrap-wrap">
        <div class="field has-addons">
          <div class="control">
            <a class="button is-info" @click="sizeDown"> - Size Small </a>
          </div>
          <div class="control">
            <input type="number" v-model="width" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="sizeUp"> + Size Large </a>
          </div>
        </div>
        <div class="field has-addons">
          <div class="control">
            <a class="button is-info" @click="angleDown"> - Rotete </a>
          </div>
          <div class="control">
            <input type="number" v-model="angle" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="angleUp"> + Rotate </a>
          </div>
        </div>
        <div class="field has-addons">
          <div class="control">
            <a class="button is-info" @click="durationUp"> - Cycle Speed </a>
          </div>
          <div class="control">
            <input type="number" v-model="duration" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="durationDown"> + Cycle Speed </a>
          </div>
        </div>
      </div>
    </div>
    <img
      alt="Vue logo"
      src="../assets/mark.svg"
      v-bind:style="{
        width: width + 'px',
        transform: 'rotate(' + angle + 'deg)',
        animationDuration: duration + 'ms',
      }"
    />
  </div>
</template>

<script>
export default {
  name: "Eye",
  data() {
    return {
      width: 1000,
      angle: 0,
      duration: 1000,
    };
  },
  methods: {
    sizeUp() {
      this.width += 100;
    },
    sizeDown() {
      this.width -= 100;
    },
    angleUp() {
      this.angle += 15;
    },
    angleDown() {
      this.angle -= 15;
    },
    durationUp() {
      this.duration += 100;
    },
    durationDown() {
      this.duration -= 100;
    },
  },
};
</script>

<style scoped>
img {
  display: block;
  margin: 0 auto;
  animation: anime1 1s ease infinite alternate;
  margin:300px auto;
}

@keyframes anime1 {
  0% {
    filter: blur(0px);
  }
  30% {
    filter: blur(0.5px);
  }
  100% {
    filter: blur(2px);
  }
}
</style>
