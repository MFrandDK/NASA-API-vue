<template>
  <div class="navMain">
    <NasaNav/>
    <div class="contentMain">
      <nApod/>
    </div>
    <NasaFooter/>

  </div>
</template>

<script>


import NasaFooter from './components/NasaFooter.vue';
import NasaNav from './components/NasaNav.vue'
import nApod from './components/nApod.vue';


export default {
    name: "App",
    components: { NasaFooter, NasaNav, nApod }
}
</script>

<style>
  * {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
	background: black;
	display: flex;
	flex-direction: column;
	align-items: center;
}


.navMain {
  display: flex;
	flex-direction: column;
	align-content: center;
	color: black;
	justify-content: center;
	justify-items: center;
	width: 100vw;
  margin-bottom: 4rem;
}
.contentMain {
  display: block;
	margin: 0 auto;
  max-width: 100%;
}
</style>
