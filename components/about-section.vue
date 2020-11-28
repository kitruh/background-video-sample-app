<template>
  <div id='content'>
    <div class='info-section-container'>
      <div class="info-section-title animate__animated animate__fadeInLeft">ABOUT</div>
      <div class="trait-highlights">
        <div class="individual-trait"
             data-aos="fade-right"
             data-aos-offset="100"
             data-aos-delay="50"
             data-aos-duration="1000"
             data-aos-once="true"
             data-aos-easing="ease-in-out"
        >
          <div class="trait-img-wrapper">
            <client-only>
              <kinesis-container>
                <kinesis-element :strength="this.strength" type="depth">
                  <img class="trait-img" src="~assets/icon-experienced.png"/>
                </kinesis-element>
              </kinesis-container>
            </client-only>
          </div>
          <div class="individual-trait-title">Experienced</div>
          <div class="individual-trait-body">I have designed and implemented multiple enterprise applications for both
            private and public sector entities.
          </div>
        </div>
        <div class="individual-trait"
             data-aos="fade-right"
             data-aos-offset="100"
             data-aos-delay="50"
             data-aos-duration="1000"
             data-aos-once="true"
             data-aos-easing="ease-in-out">
          <div class="trait-img-wrapper">
            <client-only>
              <kinesis-container>
                <kinesis-element :strength="this.strength" type="depth"><img class="trait-img" src="~assets/icon-imaginative.png"/>
                </kinesis-element>
              </kinesis-container>
            </client-only>
          </div>
          <div class="individual-trait-title">Imaginative</div>
          <div class="individual-trait-body">Your website should not only be beautiful, it should be stunning.
          </div>
        </div>
        <div class="individual-trait"  data-aos="fade-left"
             data-aos-offset="100"
             data-aos-delay="50"
             data-aos-once="true"
             data-aos-duration="1000"
             data-aos-easing="ease-in-out">
          <div class="trait-img-wrapper">
            <client-only>
              <kinesis-container>
                <kinesis-element :strength="this.strength" type="depth"><img class="trait-img" src="~assets/icon-heartfelt.png"/>
                </kinesis-element>
              </kinesis-container>
            </client-only>
          </div>
          <div class="individual-trait-title">Heartfelt</div>
          <div class="individual-trait-body">Compassion & positivity delivered on a platter to your team.
          </div>
        </div>
        <div class="individual-trait"  data-aos="fade-left"
             data-aos-offset="100"
             data-aos-delay="50"
             data-aos-once="true"
             data-aos-duration="1000"
             data-aos-easing="ease-in-out">
          <div class="trait-img-wrapper">
            <client-only>
              <kinesis-container>
                <kinesis-element :strength="this.strength" type="depth">
                  <img class="trait-img" src="~assets/icon-dynamic.png"/>
                </kinesis-element>
              </kinesis-container>
            </client-only>
          </div>
          <div class="individual-trait-title">Dynamic</div>
          <div class="individual-trait-body">I adapt to meet your needs, regardless of what your business, culture, or
            timeline looks like.
          </div>
        </div>
      </div>
      <div class="photo-section"
           data-aos="fade-right"
           data-aos-offset="100"
           data-aos-delay="50"
           data-aos-once="true"
           data-aos-duration="1000"
           data-aos-easing="ease-in-out"
      >
        <div class="photo-section-img-wrapper">
          <client-only>
            <kinesis-container>
              <kinesis-element :strength="10" type="depth">
                <img class="headshot-img" src="~assets/max-headshot.png"/>
              </kinesis-element>
            </kinesis-container>
          </client-only>
        </div>

        <div class="photo-section-text">
          <div class="photo-section-text-wrapper">
            I'm a full-stack Developer for <a class="photo-section-link" target="_blank" href="https://www.hmbnet.com">HMB</a>
            in Columbus, OH. Go Bucks! As a life long geek, I stop at nothing to get the job done.
            I'm most passionate about building beautiful, innovative UI's, as well as chasing my 1-year-old down the hallway.
          </div>

        </div>

      </div>
      <div class="percentage-section">
        <percentage-item name="Javascript" :percentage="95" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="CSS" :percentage="90" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="HTML" :percentage="85" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="React" :percentage="65" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="Vue" :percentage="80" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="Ember" :percentage="80" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="Spring" :percentage="55" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="Java" :percentage="80" :fadeDirection="this.fadeLeft"/>
        <percentage-item name="SQL" :percentage="70" :fadeDirection="this.fadeLeft"/>
      </div>
    </div>
  </div>
</template>

<script>
import PercentageItem from '@/components/percentage-item';
import {KinesisContainer, KinesisElement} from 'vue-kinesis';

export default {
  name: 'about-section',
  data(){
    return{
      strength: 10,
      fadeLeft: 'fade-left',
      fadeRight: 'fade-right'
    }
  },
  components: {PercentageItem, KinesisContainer, KinesisElement},
};
</script>

<style scoped>

.photo-section-text {
  display: flex;
  justify-content: center;
  font-family: "Fira Sans", sans-serif;
  font-weight: 300;

}

.photo-section-text-wrapper {
  max-width: 30em;
  text-align: center;
}

.photo-section-link {
  color: #D35074;
  text-decoration: none;
}

.photo-section {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows:1fr .4fr;
  grid-gap: 1em;
}

.photo-section-img-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.individual-trait {
  display: grid;
  justify-content: center;
  font-family: "Fira Sans", sans-serif;
  grid-template-rows: 1fr .3fr 1.2fr;
  grid-template-columns:1fr;
}

.individual-trait-title {
  font-weight: 800;
  font-size: 1.5em;
  justify-content: center;
  align-items: center;
  display: flex;
}

.individual-trait-body {
  font-weight: 400;
  display: flex;
  text-align: center;
}

.trait-img-wrapper {
  justify-content: center;
  align-items: center;
  display: flex;
  margin-bottom: .5em;
}

.trait-img {
  width: 7em;
}

.headshot-img {
  width: 300px;
}

.info-section-title {
  grid-column: 1/3;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Fira Sans", sans-serif;
  color: black;
  font-size: 3em;
  font-weight: 600;
  margin-bottom: 1em;
  margin-top: .5em;
}

.trait-highlights {
  grid-column: 1/3;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-gap: 50px;
}

#content {
  min-height: -webkit-fill-available;
  background-color: white;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  padding-bottom: 5em;
}

.info-section-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 2fr 4fr 5fr;
  width: 80vw;
  grid-column-gap: 3em;
}

@media screen and (max-width: 992px) {
  #content {
    width: 100%;
  }

  .info-section-container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: .2fr 2fr 1fr .8fr;
  }

  .trait-highlights {
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 0;
    grid-column: 1;
  }

  .info-section-title {
    grid-column: 1;
    margin-top: 1em;
  }

  .individual-trait {
    grid-template-rows: 1fr .3fr .8fr;
    grid-template-columns:1fr;
  }

  .photo-section {
    grid-template-columns: 1fr;
    grid-template-rows: 4fr 2fr;
    grid-gap: 0;
  }

}
</style>
