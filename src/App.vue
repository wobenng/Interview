<template>
    <div id="app">
        <Carousel />
        <Vr />
        <Reservation />
    </div>
</template>

<script>
import Carousel from './components/Carousel.vue';
import Vr from './components/Vr.vue';
import Reservation from './components/Reservation.vue';

export default {
    name: 'App',
    components: {Carousel,Vr,Reservation},
}
</script>

<style scoped lang="scss">
*{
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
}
</style>
