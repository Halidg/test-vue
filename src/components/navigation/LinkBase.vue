<template>
  <a 
  class="nav-link"
  @click="linkTo"
  :class="{
    'nav-link__menu' : style === 'menu',
    'nav-link__active' : style === 'active',
    'nav-link__icons'  : style === 'icons',
    'nav-link__footer' : style === 'footer'  
  }"
  >
    <slot />
  </a>  
</template>

<script>
export default {
  emits:['click'],
  props: {
    style: String  
  },
  methods: {
    linkTo() {
      this.$emit('click')    
    }    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.nav-link {
  padding-right: 18px;
  font-weight: 400;
  position: relative;
  font-style: normal;
  font-family: 'Tele 2';
  font-weight: 400;
  font-size: 14px;
  line-height: 18px;
  color: #7C8792;
  
  &:hover {
    cursor: pointer;
    color: #1F2229;
  }
  &:after {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    bottom: -1px;
    width: 0;
    height: 2px;
    background-color: #000000;
    transition: width 0.5s;  
  }
  &:hover::after {
    content: "";
    width: 85%;
    display: block;
    position: absolute;
    left: 0;
    bottom: -3px;
    height: 2px; 
    background-color: #000000; 
    transition: width 0.5s;  
  }
  
  @include desktop() {
    margin-bottom: 24px;
    border-bottom: 1px solid #EDEDED;  

    &:after {
      display: none;
    }

    &:hover::after {
      display: none;
    }
  }
}
</style>