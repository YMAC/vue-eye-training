<template>
  <div class="about">
    <section class="hero is-primary">
      <div class="hero-body">
        <p class="title">Eye Training</p>
        <p class="subtitle">
This image is useful for vision training. Watching for 3 minutes every day will restore your eyesight. Please relax and have a look.</p>
      </div>
    </section>
    <Eye />
  </div>
</template>

<script>
// @ is an alias to /src
import Eye from "@/components/Eye.vue";

export default {
  name: "Triangle",
  components: {
    Eye,
  },
};
</script>
