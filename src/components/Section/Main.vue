<template>
  <section class="main">
    <div class="container">
      <Navigation></Navigation>
    </div>
  </section>  
 
</template>

<script>
import Navigation from '../Navigation/Navigation'

export default {
  components: {
    Navigation
}  
}
</script>

<style lang="scss" scoped>
.main {
  padding-top: 15px;
}
</style>