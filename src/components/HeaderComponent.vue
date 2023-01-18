<template>
  <header>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li
              class="nav-item"
              v-for="(link, index) in menuLinks"
              :key="index"
            >
              <router-link
                active-class="active"
                :to="{ name: link.routeName }"
                class="nav-link"
              >
                {{ link.label }}
              </router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      menuLinks: [
        {
          label: "Home",
          routeName: "home",
        },
        {
          label: "Projects",
          routeName: "projects",
        },
        {
          label: "AbutUs",
          routeName: "AboutUs",
        },
        {
          label: "Contact",
          routeName: "ContactUs",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
