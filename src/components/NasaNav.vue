<template>
  <nav>
    <div class="flex">
      <div>
        <a href="https://www.nasa.gov/"><img src="../assets/logo.png" alt="Nasa Logo" class="logo" />
        </a>
        <h3> NASA - Picture of The Day</h3>
      </div>

    </div>
  </nav>

</template>

<script>


export default {
  name: 'NasaNav',
}

</script>

<style scoped>
nav {
  padding-top: 25px;
  display: flex;
  position: absolute;
  top: 0px;
  height: 70px;
  right: 0;
  left: 0;
  justify-content: center;
  background: rgba(32, 29, 29, 0.633);
  padding-bottom: 20px;
}

div.flex {
  justify-content: center;
  display: flex;
  min-width: 100vw;
}

div {
  display: flex;
  align-items: center;
}

a {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 45px;
  width: 45px;
  border-radius: 30px;
  margin-bottom: 3px;
}

.logo {
  width: 60px;
  padding-bottom: 0px;
  height: auto;
}

h3 {
  color: rgb(223, 223, 223);
  margin-left: 10px;
  font-size: 20px;
  margin-bottom: 3px;
  cursor: default;
  font-weight: 400;
}
</style>
