<template>
  <span class="go-back">
    <button @click="goBack">&#8678; go back</button>
  </span>
</template>
<script>
export default {
  methods: {
    goBack() {
      return this.$router.go(-1);
    }
  }
};
</script>

<style scoped>
.go-back {
  display: flex;
  cursor: pointer;
}
button {
  border: 10;
  padding: 10px;
  margin: 10px 0 0 10px;
}
</style>
