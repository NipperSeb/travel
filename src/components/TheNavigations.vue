<template>
  <div class="myNavigation">
    <nav
      class="navbar sticky-top navbar-expand-lg navbar-light"
      style="background-color: #e3f2fd;"
    >
      <a class="navbar-brand">
        <img
          src="@/assets/logo6.png"
          width="90"
          height="40"
          class="d-inline-block align-bottom"
          alt="logo"
        />
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <li class="nav-item">
            <router-link to="/" class="nav-item nav-link text-dark">
              Home
            </router-link>
          </li>
          <li
            v-for="destination in destinations"
            :key="destination.name"
            class="nav-item"
          >
            <router-link
              class="nav-item nav-link text-dark"
              :to="{
                name: 'DestinationDetails',
                params: { slug: destination.slug }
              }"
            >
              {{ destination.name }}
            </router-link>
          </li>
          <li class="nav-item">
            <router-link to="/user" class="nav-item nav-link text-dark">
              Private
            </router-link>
          </li>
          <li class="nav-item">
            <router-link to="/resume" class="nav-item nav-link text-dark">
              Resume
            </router-link>
          </li>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import store from "@/store";
export default {
  data() {
    return {
      destinations: store.destinations
    };
  }
};
</script>

<style scoped>
.myNavigation {
  position: sticky;
  top: 0;
  border-bottom: 1px solid grey;
  z-index: 1;
}
.nav-link:hover {
  text-decoration: underline;
}
</style>
