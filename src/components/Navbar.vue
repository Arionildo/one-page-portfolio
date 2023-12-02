<template>
  <nav class="navbar navbar-expand-lg border-navbar" :class="{ 'navbar-light': isLightTheme, 'navbar-dark': !isLightTheme, 'bg-light': isLightTheme, 'bg-dark': !isLightTheme }">
    <div class="container-fluid">
      <router-link to="/">
        <img src="../assets/logo.PNG" alt="Ari Escouto Software Engineer Logo" class="navbar-brand">
      </router-link>

      <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Projects</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/sobre">About</router-link>
          </li>
        </ul>
      </div>

      <div class="ml-auto">
        <button class="btn btn-outline-primary"
                :class="{ 'btn-light': isLightTheme, 'btn-dark': !isLightTheme }"
                @click="toggleTheme">
          <span v-if="isLightTheme">
            <i class="bi bi-moon"></i>
          </span>
          <span v-else>
            <i class="bi bi-sun"></i>
          </span>
        </button>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isLightTheme: false,
    };
  },
  methods: {
    toggleTheme() {
      this.isLightTheme = !this.isLightTheme;
    },
  },
};
</script>

<style scoped>
.navbar-light {
  background-color: #f8f9fa;
  color: #495057;
}

.navbar-dark {
  background-color: #343a40;
  color: #ffffff;
}

.navbar-brand {
  height: 100%;
  max-height: 65px;
  padding: 0;
}

@media (max-width: 767px) {
  .navbar-brand {
    height: 50px;
    max-height: 50px;
  }
}

.container-fluid {
  padding: 0;
}

.navbar {
  margin: 0;
  --bs-navbar-padding-y: 0;
}

.border-navbar {
  border-bottom: 2px solid #6BB3D3;
}

.btn-outline-primary {
  --bs-btn-padding-x: 1.3rem;
  --bs-btn-padding-y: 1.3rem;
  color: #ffffff;
  background-color: #6BB3D3;
  border: none;
  border-radius: initial;
}

.btn-light {
  --bs-btn-hover-bg: #212529;
  --bs-btn-active-color: #6BB3D3;
  --bs-btn-active-bg: #212529;
}

.btn-dark {
  --bs-btn-hover-bg: #ffffff;
  --bs-btn-active-color: #6BB3D3;
  --bs-btn-active-bg: #ffffff;
}
</style>
