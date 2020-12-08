<template>
  <div>
    <h1>hey {{ user }} man, what are you doing?</h1>
    <button @click="logOut" class="btn">Log out</button>
    <img class="fit-picture" src="@/assets/toilet.png" alt="manToilet" />
  </div>
</template>
<script>
import store from "@/store";
export default {
  data() {
    return {
      user: store.user
    };
  },
  methods: {
    logOut() {
      store.user = null;
      this.$router.push("/");
    }
  }
};
</script>
<style>
.btn {
  display: block;
  background-color: green;
  color: white;
  padding: 10px;
  margin-left: auto;
  margin-right: auto;
}
.fit-picture {
  display: block;
  width: 250px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 10px;
}
</style>
