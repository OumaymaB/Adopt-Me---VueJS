<template>
  <div id="nav">
    <router-link :to="{ name: 'Home' }" id="animals">AnimalS</router-link>
    <router-link :to="{ name: 'About' }" id="about">About</router-link>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
$color: aqua;

#nav {
  padding: 30px;
  display: flex;
  justify-content: space-between;
  background-color: black;
  border-bottom: 5px solid $color;

  #animals {
    color: $color;
    text-decoration: none;
    font-weight: bold;
    font-size: 30px;
  }

  #about {
    color: $color;
    text-decoration: none;
    font-size: 20px;
    font-weight: bold;
  }
}
</style>