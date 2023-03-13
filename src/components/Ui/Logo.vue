<template>
  <img class="logo" src="@/assets/logo/Logo.svg" alt="logo">  
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
 @import "@/styles/mixins.scss";
.logo {
  @include phones() {
    max-width: 140px;
  }
}
</style>