<template>
    <div class="percentage-wrapper"
         :data-aos="this.fadeDirection"
         data-aos-offset="100"
         data-aos-delay="50"
         data-aos-once="true"
         data-aos-duration="1000"
         data-aos-easing="ease-in-out"
         :data-aos-id="this.name">
      <div class="percentage-name">{{ name }}</div>
      <div class="percentage-progress-bar">
        <div class="progress-bar" :style="this.style">
        </div>
      </div>
      <div class="percentage-value">{{ percentage }}%</div>
    </div>
</template>

<script>
export default {
  name: 'percentage-item',
  props: {
    name: '',
    percentage: '',
    fadeDirection: ''
  },
  computed: {
    style () {
      return `width: ${this.percentage}%;`
    }
  },
  data(){
    return {
      percentageAltered: ''
    }
  },
  mounted(){
    // const $this = this;
    // document.addEventListener(`aos:in:${this.name}`, ({ detail }) => {
    //   debugger;
    //   $this.percentageAltered = $this.percentage;
    // });
    //
    // document.addEventListener(`aos:out:${this.name}`, ({ detail }) => {
    //   debugger;
    //   $this.percentageAltered = 0;
    // });
  }
}
</script>

<style scoped>
.percentage-value {
  display: flex;
  justify-content: center;
  align-items: center;
}

.percentage-wrapper {
  width: 100%;
  font-family: "Fira Sans", sans-serif;
  display: grid;
  grid-template-columns: 2fr 8fr 1fr;
  grid-template-rows:1fr;
  background-color: #EEEEEE;
  color: #666;
  margin-bottom: 1em;
}

.progress-bar {
  background: #2E2642;
  height: 2em;
  transition: 1s;
}

.percentage-name {
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  background-color: #593E72;
}

@media screen and (max-width: 992px) {
  .percentage-name {
    font-size: .75em;
  }

  .percentage-wrapper {
    grid-template-columns: 3fr 8fr 1fr;
  }

  .percentage-value {
    margin-right: 1em;
  }
}
</style>
