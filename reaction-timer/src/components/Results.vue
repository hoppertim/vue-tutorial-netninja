<template>
  <p>Reaction time: {{ this.score }} ms</p>
</template>

<script>
export default {
  props: {
    score: Number,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>
