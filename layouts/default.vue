<template>
  <div class="layout">
    <div class="layout__content">
      <Nuxt />
    </div>
    <div class="layout__navigaton">
      <Navigation />
    </div>
  </div>
</template>

<script>
import Navigation from '@/components/Navigation'
export default {
  components: {
    Navigation
  }
}
</script>

<style>
  body{
    background: #000;
    font-family: Helvetica, sans-serif;
    position: relative;
    text-transform: uppercase;
  }
  .layout__navigaton{
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
  }

  .layout__content{
    font-size: 100px;
    font-weight: bold;
    color: #fff;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    min-height: 100vh;

    display: flex;
    justify-content: center;
    text-align: center;
    align-items: center;
  }

</style>
