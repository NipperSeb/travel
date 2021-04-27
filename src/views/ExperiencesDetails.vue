<template>
  <div>
    <section class="container-fluid" v-scrollanimation id="page">
      <div class="row">
        <div class="col-sm">
          <div
            id="carouselExampleIndicators"
            class="carousel slide"
            data-ride="carousel"
          >
            <ol class="carousel-indicators bg-primary">
              <li
                data-target="#carouselExampleIndicators"
                data-slide-to="0"
                class="active"
              ></li>
              <li
                data-target="#carouselExampleIndicators"
                data-slide-to="1"
              ></li>
              <li
                data-target="#carouselExampleIndicators"
                data-slide-to="2"
              ></li>
              <li
                data-target="#carouselExampleIndicators"
                data-slide-to="3"
              ></li>
            </ol>
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img
                  class="d-block img-fluid"
                  :src="require(`@/assets/${experience.carousel.photo4}`)"
                  :alt="experience.name"
                />
              </div>
              <div class="carousel-item">
                <img
                  class="d-block img-fluid"
                  :src="require(`@/assets/${experience.carousel.photo1}`)"
                  :alt="experience.name"
                />
              </div>
              <div class="carousel-item">
                <img
                  class="d-block img-fluid"
                  :src="require(`@/assets/${experience.carousel.photo2}`)"
                  :alt="experience.name"
                />
              </div>
              <div class="carousel-item">
                <img
                  class="d-block img-fluid"
                  :src="require(`@/assets/${experience.carousel.photo3}`)"
                  :alt="experience.name"
                />
              </div>
            </div>
            <a
              class="carousel-control-prev"
              href="#carouselExampleIndicators"
              role="button"
              data-slide="prev"
            >
              <span
                class="carousel-control-prev-icon bg-primary"
                aria-hidden="true"
              ></span>
              <span class="sr-only">Previous</span>
            </a>
            <a
              class="carousel-control-next"
              href="#carouselExampleIndicators"
              role="button"
              data-slide="next"
            >
              <span
                class="carousel-control-next-icon bg-primary"
                aria-hidden="true"
              ></span>
              <span class="sr-only">Next</span>
            </a>
          </div>
        </div>
        <div class="col-sm">
          <div class="alert alert-primary" role="alert">
            {{ experience.name }}
          </div>
          <div class="experience-detail">
            <p>{{ experience.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import store from "@/store.js";

export default {
  props: {
    slug: {
      type: String,
      required: true
    },
    experienceSlug: {
      type: String,
      required: true
    }
  },
  computed: {
    destination() {
      return store.destinations.find(
        destination => destination.slug === this.slug
      );
    },
    experience() {
      return this.destination.experiences.find(
        experience => experience.slug === this.experienceSlug
      );
    }
  }
};
</script>
<style scoped>
section {
  box-sizing: border-box;
  margin-top: 50px;
}
img {
  object-fit: cover;
  background-size: 100% 100%;
  border: 1px solid #ccc;
  padding: 15px;
  /*height: 400px;*/
}
.alert {
  font-weight: bold;
  font-size: 2em;
}

.before-enter {
  opacity: 0;
  transform: translateX(100px);
  transition: all 1s cubic-bezier(0.39, 0.575, 0.565, 1);
}

.enter {
  opacity: 1;
  transform: translate(0px);
}
</style>
