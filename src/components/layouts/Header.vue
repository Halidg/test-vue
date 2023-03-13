<template>
  <header class="header">
    <div class="container">
      <div class="header__content">
        <div class="header__logo">
          <Logo />
        </div>
        <div class="header__location">
          <img class="header__location-img" src="../../assets/icons/location.svg" alt="location">
          <span class="header__location-info">Москва и область</span>   
        </div>
        <div class="header__bell">
          <img class="header__bell-img" src="../../assets/icons/Notification-Bell.svg" alt="Notification">
          <span class="header__bell-notification"></span>
        </div>
        <div class="header__burger">
          <Burger @click-burger="showMenu" :show="showing" />
        </div>
      </div>
         <BurgerMenu :show="showing">
           <Navigation :style="'mobile'"/> 
         </BurgerMenu>
    </div>
  </header>  
</template>

<script>
import Logo from '../Ui/Logo.vue'
import Navigation from '../navigation/Navigation'
import BurgerMenu from '../Ui/BurgerMenu.vue'
import Burger from '../Ui/Burger.vue'

export default {
  components: {
    Logo,
    Navigation,
    BurgerMenu,
    Burger  
  },
  data() {
    return {
      showing: false  
    }  
  },
  methods: {
    showMenu() {
      this.showing = !this.showing 
    }  
  },
  computed: {
    burgerSrc() {
      return this.showing ? require('@/assets/icons/close.svg') : require('@/assets/icons/burger.svg') 
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.header {
  width: 100%;
  z-index: 1000;
  background: #1F2229;
  transition: 0.5s;
  padding: 19px 0;

  @include phones() {
    padding: 5px 0;                 
  }
  
  &__content {
    display: flex;
    justify-content: center;
    align-items: center;   
  }

  &__logo {
    margin-right: auto;
    z-index: 1000;
  }

  &__location {
    display: flex;
    align-items: center;
    justify-content: center;

    @include desktop() {
      display: none;
    }

    &-img {
      margin-right: 13px;
    }

    &-info {
      font-style: normal;
      font-weight: 400;
      font-size: 14px;
      font-family: 'Tele 2';
      line-height: 18px;
      color: #7C8792;
    }
  }

  &__bell {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;

    @include desktop() {
      margin-right: 13px;
    }

    &-img {
      margin-left: 47px;
    }

    &-notification {
      position: absolute;
      z-index: 1;
      top: 5px;
      right: 7px;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background-color: rgba(63, 203, 255, 1);
    }
  }

  &__action {
    margin-left: auto;
  }
 
  &__burger {
    display: none;
    
    @include desktop() {
      display: block;
      z-index: 1000;  
    }
  }
}
</style>