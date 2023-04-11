<template>
  <div class="menu" :class="{'menu_show': show}">
    <slot />
    <div class="menu__location" :class="{'menu_show': show}">
      <slot name="location" />
    </div>  
  </div>
</template>

<script>

export default {
  props: {
    show: Boolean
  },
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.menu {
  position: fixed;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 55px 15px;
  transition-duration: 300ms;

  &__location {
    display: flex;
    align-items: center;
    margin-top: auto;
  }

  &_show {
    left: 0;
  }
}
</style>