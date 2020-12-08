<template>
  <div class="destination">
    <GoBack />
    <section class="destination--box">
      <h1>{{ destination.name }}</h1>
      <div class="container-fluid destination-details">
        <div class="d-flex">
          <img
            class="d-none d-lg-block"
            :src="require(`@/assets/${destination.image}`)"
            :alt="destination.name"
          />
          <p>{{ destination.description }}</p>
        </div>
      </div>
    </section>
    <section class="experiences">
      <h2>My experiences in {{ destination.name }}</h2>
      <div class="container-fluid cards" id="experience">
        <div class="row d-flex justify-content-center">
          <div
            v-for="experience in destination.experiences"
            :key="experience.slug"
            class="card"
          >
            <router-link
              :to="{
                name: 'experiencesDetails',
                params: { experienceSlug: experience.slug },
                hash: '#experience'
              }"
            >
              <img
                v-scrollanimation
                :src="require(`@/assets/${experience.image}`)"
                :alt="experience.name"
              />
              <span class="card__text">
                {{ experience.name }}
              </span>
            </router-link>
          </div>
        </div>
      </div>

      <router-view :key="$route.path" />
    </section>
    <div>
      <Footer />
    </div>
  </div>
</template>

<script>
import store from "@/store.js";
import GoBack from "@/components/GoBack";
import Footer from "@/components/Footer";

export default {
  components: {
    GoBack,
    Footer
  },
  data() {
    return {};
  },
  props: {
    slug: {
      type: String,
      required: true
    }
  },
  computed: {
    destination() {
      return store.destinations.find(
        destination => destination.slug === this.slug
      );
    }
  }
};
</script>
<style lang="scss" scoped>
.destination-details {
  box-sizing: border-box;
  margin: 10px;
  border: 5px solid rgb(62, 175, 184);
  border-radius: 10px;
  background-color: rgb(245, 234, 234);
  img {
    max-width: 400px;
    height: auto;
    width: 100%;
    max-height: 200px;
    margin: 10px;
    border-radius: 12px;
    border-style: solid;
    border-color: black;
  }
}
p {
  margin: 0 40px;
  font-size: 20px;
  text-align: left;
  margin-top: 15px;
}
h1,
h2 {
  color: rgb(62, 175, 184);
  font-weight: bold;
}
.cards img {
  max-height: 150px;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
  max-width: 150px;
  height: 100%;
  &:hover {
    box-shadow: 0 0 2px 1px rgba(0, 140, 186, 0.5);
  }
}
a {
  height: 100%;
}
.card {
  padding: 0 20px;
  position: relative;
  margin: 10px;
}
.card__text {
  position: absolute;
  top: 20%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: rgb(121, 10, 10);
  font-weight: bold;
  text-decoration: none;
}

.destination {
  background-color: rgb(247, 239, 231);

  &--box {
    padding: 40px 0;
    margin-right: 15px;
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
