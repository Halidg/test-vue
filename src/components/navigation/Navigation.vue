<template>
  <nav class="nav" :class="{
    'nav__mobile' : style === 'mobile'
  }">
    <link-base>Преимущества Tele2</link-base>
    <link-base>Тарифы</link-base>
    <link-base>Акции и спецпредложения</link-base>
    <link-base>Промотариф Tele2</link-base>
    <link-base>Технология eSIM</link-base>
    <link-base>Подключение нового абонента US</link-base>
  </nav>  
</template>

<script>
import LinkBase from './LinkBase.vue'

export default {
  props:{
    style: String
  },
  components: {
    LinkBase,
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.nav {
  display: flex;
  position: relative;
  gap: 18px;

  @include desktop() {
    display: none;           
  }
  
  &__mobile {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-top: 24px;
  }
}
</style>