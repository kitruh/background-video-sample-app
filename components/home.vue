<template>
  <div>
    <div class="main-section">
      <video autoplay muted loop id="myVideo">
        <source src="~assets/ezrakimwedding.mp4" type="video/mp4">
      </video>
      <div class="main-title">
        <span class="ek">EzraKim</span>
        <span class="creative-text">Creative</span>
      </div>
    </div>


  </div>
</template>

<script>

export default {
  name: "newHome",
  data(){
    return {
      component: 'about'
    }
  },
  methods: {
    switchComponent(componentName){
      this.component = componentName
    }
  },
};
</script>

<style  scoped>
@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;700;800&display=swap");
.main-section{
  height:100vh;
  overflow:hidden;
  position:absolute;
  width:100%;
}

/*video{*/
/*  position:absolute;*/
/*  z-index:1;*/
/*  width:100vw;*/
/*}*/

video {
  z-index:1;
  height: 100%;
  width: 177.77777778vh; /* 100 * 16 / 9 */
  min-width: 100%;
  min-height: 56.25vw;
  position: absolute;
  left: 50%; /* % of surrounding element */
  top: 50%;
  transform: translate(-50%, -50%); /* % of current element */
}

.main-title{
  z-index:2;
  position:absolute;
  display:flex;
  width:100%;
  height:100vh;
  justify-content: center;
  align-items: center;
}
.ek{
  font-family: 'Roboto', sans-serif;
  font-size:4em;
  font-weight:900;
  color:white;
}
.creative-text{
  font-family: 'Roboto', sans-serif;
  font-size:4em;
  color:white;
}


</style>
