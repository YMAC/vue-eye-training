<template>
  <div class="home">
    <section class="hero is-primary">
      <div class="hero-body">
        <p class="title">Eye Training</p>
        <p class="subtitle">
          This image is useful for vision training. Watching for 3 minutes every
          day will restore your eyesight. Please relax and have a look.
        </p>
      </div>
    </section>

    <div class="box">
      <div class="is-flex is-justify-content-space-between is-flex-wrap-wrap">
        <div class="field has-addons">
          <div class="control">
            <a class="button is-info" @click="sizeDown"> - Size Small </a>
          </div>
          <div class="control">
            <input type="number" v-model="height" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="sizeUp"> + Size Large </a>
          </div>
        </div>
        <div class="field has-addons">
          <div class="control">
            <a class="button is-info" @click="marginDown"> - Margin </a>
          </div>
          <div class="control">
            <input type="number" v-model="mb" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="marginUp"> + Margin </a>
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
            <a class="button is-info" @click="durationUp"> - Cycle </a>
          </div>
          <div class="control">
            <input type="number" v-model="duration" class="input" />
          </div>
          <div class="control">
            <a class="button is-danger" @click="durationDown"> + Cycle </a>
          </div>
        </div>
      </div>
    </div>
    <div
      class="box data"
      :style="{
        maxWidth: maxWidth + 'px',
        transform: 'rotate(' + angle + 'deg)',
      }"
    >
      <div
        v-for="i in range"
        :key="i"
        class="bar"
        :style="{
          height: height + 'px',
          marginBottom: mb + 'px',
          animationDuration: duration + 'ms',
        }"
      >
        &nbsp;
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Home",
  data() {
    return {
      duration: 1000,
      height: 10,
      range: 50,
      mb: 10,
      angle: 0,
      maxWidth: 800,
    };
  },
  methods: {
    sizeUp() {
      this.height += 1;
    },
    sizeDown() {
      this.height -= 1;
    },
    marginUp() {
      this.mb += 1;
    },
    marginDown() {
      this.mb -= 1;
    },
    angleUp() {
      this.angle += 45;
    },
    angleDown() {
      this.angle -= 45;
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
.bar {
  animation: anime1 1s ease infinite alternate;
  width: 100%;
  background: #000;
  margin-bottom: 5px;
}
.data {
  margin: 100px auto;
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
