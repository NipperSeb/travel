<template>
  <section class="home">
    <h1>
      Welcome to my crazy world!!!
    </h1>
    <div class="container-fluid">
      <img alt="Seb head" class="rounded-circle" src="@/assets/avatar.jpg" />
      <h1>"Sebmaster"</h1>
      <p>
        This site is my FrontEnd project. It is for my friends, family,
        recruiter, coworker, police, tax department and anyone with time to
        spare. <i class="emoji">&#128540;</i><br />
        You will find on it a description of the activities that enrich my daily
        life.
      </p>
    </div>

    <div class="container-fluid destinations">
      <div class="row justify-content-center">
        <div
          class="box"
          v-for="destination in destinations"
          :key="destination.name"
        >
          <router-link
            :to="{
              name: 'DestinationDetails',
              params: { slug: destination.slug }
            }"
          >
            <h2>{{ destination.name }}</h2>
          </router-link>
          <figure>
            <router-link
              :to="{
                name: 'DestinationDetails',
                params: { slug: destination.slug }
              }"
            >
              <img
                v-scrollanimation
                :src="require(`@/assets/${destination.image}`)"
                :alt="destination.name"
              />
            </router-link>
          </figure>
        </div>
      </div>
    </div>
    <Footer />
  </section>
</template>

<script>
// @ is an alias to /src
import store from "@/store.js";
import Footer from "@/components/Footer";
export default {
  name: "home",
  components: {
    Footer
  },
  data() {
    return {
      destinations: store.destinations
    };
  }
};
</script>

<style lang="scss" scoped>
.home {
  box-sizing: border-box;
  background-color: rgb(247, 239, 231);
  height: 100vh;
  padding: 0;
  margin: 0;
}
a {
  text-decoration: none;
}
a:hover,
a:visited {
  text-decoration: underline;
}

h1 {
  color: rgb(62, 175, 184);
  margin-left: 30px;
}

img {
  width: 140px;
  height: 140px;
  margin-top: 15px;
  border-radius: 12px;
  border-style: solid;
  border-color: black;
  padding: 10px;
}

.destinations {
  background-color: rgb(247, 246, 187);
  //margin: 30px;
  .box {
    background-color: bisque;
    width: 250px;
    margin: 30px;
    border-radius: 12px;
    h2 {
      margin-top: 15px;
      color: rgb(62, 175, 184);
    }
  }
}

.before-enter {
  opacity: 0;
  transform: scale(0.5) rotateZ(-25deg);
  transition: all 1s ease-out;
}

.enter {
  opacity: 1;
  transform: scale(1) rotateZ(0deg);
}
</style>
