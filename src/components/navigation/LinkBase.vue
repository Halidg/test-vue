<template>
  <a 
  class="nav-link"
  @click="linkTo"
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
 
  &:hover::after {
    content: "";
    width: 100%;
    display: block;
    position: absolute;
    left: 0;
    bottom: -12px;
    height: 2px; 
    background-color: #000000; 
    
  }
  
  @include desktop() {
    border-bottom: 1px solid #EDEDED;
    padding-bottom: 8px;

    &:hover::after {
      display: none;
    }
  }
}
</style>