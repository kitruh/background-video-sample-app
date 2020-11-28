<template>
  <svg @mouseover=this.hover  @mouseleave=this.stopHover
       width="3em"
       viewBox="0 0 464 156"
       version="1.1"
       xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xml:space="preserve" xmlns:serif="http://www.serif.com/" style="fill-rule:evenodd;clip-rule:evenodd;stroke-linejoin:round;stroke-miterlimit:2;">
    <g transform="matrix(1,0,0,1,-269,-114)">
        <rect class="rect1" :x=this.rect1.x :y=this.rect1.y :width=this.rect1.width :height=this.rect1.height  />
      <g transform="matrix(0.5,0,0,1,366.5,104)">
        <rect class="rect2" :x=this.rect2.x :y=this.rect2.y :width=this.rect2.width :height=this.rect2.height  />
        </g>
    </g>
</svg>
</template>

<script>
export default {
  name: 'hamburger-modern',
  data(){
    return{
      rect1:{
        target: {
          x:269,
          y: 114,
          width:464,
          height:52,
          style:"fill:white;"
        },
          x:269,
          y: 114,
          width:464,
          height:52,
          style:"fill:white;"

      },
      rect2:{
        target: {
          x:269,
          y: 114,
          width:464,
          height:52,
          style:"fill:white;"
        },
        x:269,
        y: 114,
        width:464,
        height:52,
        style:"fill:white;"

      }
    }
  },
  created(){
    // this.animate(this.rect1.target.width, 'width', this.rect1,600);
    // this.animate(this.rect2.target.width, 'width', this.rect2,600);
  },
  methods:{
    animate(endValue,propertyName,element,timeout){
      // const difference = endValue - element[propertyName]
      // if(difference > 0){
      //   for(let i = 0; i < difference; i++){
      //     setTimeout(function(){
      //       element[propertyName]++
      //     }, timeout);
      //   }
      // }else if(difference < 0){
      //   for(let i = difference; i < 0; i++){
      //     setTimeout(function(){
      //       element[propertyName]--
      //     }, timeout);
      //   }
      // }

    },
    hover(){
      this.animate(this.rect1.target.width + 20, 'width', this.rect1,600);
      this.animate( this.rect1.target.x - 20, 'x', this.rect1,600);
    },
    stopHover(){
      //this.animate(this.rect1.target.width - 20, 'width', this.rect1,600);

    }
  }
}
</script>

<style scoped>
.rect1 {
  animation: showrect1 3s ease;
}
.rect2 {
  animation: showrect2 3s ease;
}

.rect2,.rect1{
  fill:white;
}

@keyframes showrect1 {
  0% { opacity: 0; width:0;}
  100% { opacity: 1; width: 464;}
}

@keyframes showrect2 {
  0% { opacity: 0; width:0;}
  100% { opacity: 1; width: 464;}
}

</style>
