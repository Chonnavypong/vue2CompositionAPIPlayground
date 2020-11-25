<template>
  <div class="home">
    <computed-playground />
    <ComputedCompostionAPI />
  </div>
</template>

<script>
// @ is an alias to /src
import ComputedCompostionAPI from "../components/basic/computedCompostionAPI.vue";
import computedPlayground from "../components/basic/computedPlayground";

export default {
  name: "Basic",
  components: {
    computedPlayground,
    ComputedCompostionAPI,
  },
};
</script>
