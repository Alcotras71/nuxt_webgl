<template>
  <nav class="navigation">
    <nuxt-link to="/">Homepage</nuxt-link>
    <nuxt-link to="/about">About</nuxt-link>
  </nav>
</template>

<style>
  .navigation{
    font-size: 20px;
    padding: 40px;
    text-align: right;
  }

  .navigation a{
    padding: 10px;
    color: #fff;
    text-decoration: none;
    border: 1px solid #000;
  }

  .navigation .nuxt-link-exact-active{
    border-color: #fff;
  }
</style>