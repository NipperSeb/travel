<template>
  <div id="app">
    <TheNavigations />
    <transition name="fade" mode="out-in">
      <router-view :key="$route.path" />
    </transition>
  </div>
</template>

<script>
import TheNavigations from "@/components/TheNavigations";
export default {
  components: {
    TheNavigations
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #15171a;
}
.fade-enter-active,
.moveUp-leave-active {
  transition: opacity 1s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.input {
  border: 1px solid green;
  padding: 10px;
  margin-bottom: 20px;
}

.btn {
  background-color: green;
  color: white;
  padding: 10px;
}
</style>
