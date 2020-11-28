<template>
  <div>
    <!--    <div class="section-above"> Section Above </div>-->
    <div class="main-section">
      <video autoplay muted loop id="myVideo">
        <source src="~assets/weddingvideo.mp4" type="video/mp4">
      </video>
      <div class="main-title">
        <span class="ek">JohnDoe</span>
        <span class="creative-text">Creative</span>
      </div>
    </div>
    <!--    <div class="section-above"> Section Above </div>-->
    <!--  <div class="section-below">Section Below</div>-->

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

.section-above, .section-below{
  height:100vh;
  overflow:hidden;
  width:100%;
  display:flex;
  align-items: center;
  justify-content: center;
}

@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;700;800&display=swap");
.main-section{
  height:100vh;
  overflow:hidden;
  position:relative;
  width:100%;
}

/*video{*/
/*  position:absolute;*/
/*  z-index:1;*/
/*  width:100vw;*/
/*}*/

video {
  z-index:1;
  height: 56.25vw;
  width: 177.77vh;
  min-width: 100%;
  min-height: 100%;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
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
