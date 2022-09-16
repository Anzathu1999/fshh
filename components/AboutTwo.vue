<template>
  <!--Welcome One Start-->
  <section class="welcome-one">
    <div class="container">
      <div class="row">
        <div class="col-xl-6 col-lg-6">
          <div class="welcome-one__left">
            <div class="welcome-one__img-box">
              <img src="~images/resources/dance.png" alt="" />
              <div class="welcome-one__img-box-2">
                <img src="~images/resources/dannce.png" alt="" />
              </div>
            
            </div>
          </div>
        </div>
        <div class="col-xl-6 col-lg-6">
          <div class="welcome-one__right">
            <div class="section-title text-left">
              <span class="section-title__tagline">ABOUT US</span>
              <h2 class="section-title__title">
                FHS implements projects with multidisciplinary approach
              </h2>
            </div>
            <p class="welcome-one__right-text">
              Family Health Services (FHS) formerly PSI/Malawi is a local organization implementing programs aimed at improving lives of Malawians
            </p>
            <div class="welcome-one__our-mission-and-story" >
              <div class="welcome-one__mission-and-story-single" :style="`padding:10px;`">
                <h3><i class="fas fa-arrow-circle-right"></i>Our Mission</h3>
                <p class="welcome-one__our-mission-and-story-text">
                  To live healthier lives and to plan the families ....
.
                </p>
              </div>
              <div class="welcome-one__mission-and-story-single">
                <h3><i class="fas fa-arrow-circle-right"></i>Our Story</h3>
                <p class="welcome-one__our-mission-and-story-text">
                
We act with integrity, share what we achieve,.. 

                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!--Welcome One End-->
</template>

<script>
import countTo from "vue-count-to";
import { ObserveVisibility } from "vue-observe-visibility";
export default {
  components: { countTo },
  directives: {
    ObserveVisibility,
  },
  data() {
    return {
      startBar: false,
      startCounter: false,
    };
  },
  methods: {
    onVisibilityChange(isVisible) {
      if (isVisible) {
        this.startBar = true;
      }
    },
    onVisibilityCountChange(isVisible) {
      if (isVisible) {
        this.startCounter = true;
      }
    },
  },
};
</script>
<style scoped>
  .container{
    width:69%;
  }
  .welcome-one__img-box-2 {
  position: absolute;
  bottom: -70px;
  left: -60px;
}
.welcome-one__img-box:before {

  height: 200px;
}
.welcome-one__our-mission-and-story-text{
  color: black;
  font-weight: 400;
}
.welcome-one__right-text{
  color: black;
  font-weight: 400;
}
.section-title__title{
  font-size: 30px;
  font-weight: 600;
  line-height: 30px;
}
.section-title__tagline{
  
  padding-bottom: 20px;
}
</style>