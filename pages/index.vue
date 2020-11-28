<template>
  <div>
       <home/>
  </div>
</template>

<script>
import about from '../components/about.vue'
import contact from '../components/contact.vue'
import home from '../components/home.vue'

export default {
  name: "newHome",
  components:{
    home
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;700;800&display=swap");
.kitruh-title {
  font-family: "Fira Code", sans-serif;
  font-weight: 800;
  line-height: 1em;
}
.hunter-title-text{
  font-weight:100;
  font-family: "Fira Code", sans-serif;
  font-size: 3em;
}
.sub-title {
  font-family: "Manrope", sans-serif;
  font-weight: 300;
  line-height: 1em;
  margin-left: 0.2em;
}

.page-wrapper {
  height: 100vh;
  width: 100%;
  background: rgb(0, 250, 255);
}

.header {
  display: grid;
  grid-template-columns: 1fr;
  width: 100%;
  height: auto;
  padding: 0.5em;
  font-size: 2em;
}

.nav-left {
  color: white;
  display: flex;
  align-items: left;
  flex-direction: column;
}

.page-wrapper-2 {
  background-color: green;
  height: 100vh;
  color: white;
}

.left-link-list {
  display: flex;
  flex-direction: column;
  padding: 0.5em;
  color: white;
}
</style>
