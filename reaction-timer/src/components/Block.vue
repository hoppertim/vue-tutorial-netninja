<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
  props: {
    delay: Number,
  },
  data() {
    return {
      showBlock: false,
      startTime: null,
      endTime: null,
    };
  },
  mounted() {
    console.log("component mounted");
    setTimeout(() => {
      this.showBlock = true;
      this.startTime = Date.now();
    }, this.delay);
  },
  methods: {
    stopTimer() {
      this.endTime = Date.now();
      this.showBlock = false;
      this.$emit("end", this.endTime - this.startTime);
    },
  },
};
</script>

<style scoped>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
