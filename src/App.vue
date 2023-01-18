<template>
  <HeaderComponent></HeaderComponent>
  <div class="container">
    <router-view></router-view>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";

export default { components: { HeaderComponent } };
</script>

<style lang="scss" scoped></style>
