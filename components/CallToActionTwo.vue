<template>
  <!--Join One Start-->
  <section :class="`join-one ${className}`">
    <client-only>
      <div
        class="join-one-bg jarallax"
        data-jarallax
        data-speed="0.2"
        data-imgPosition="50% 0%"
      >
        <img
          src="~/assets/images/resources/projects/call.png"
          class="jarallax-img"
        />
      </div>
    </client-only>
    <div class="container">
      <div class="row">
        <div class="col-xl-12">
          <div class="join-one__inner">
            <h3 class="join-one__title" >
              Call to Action
            </h3>
            <p class="join-one__body" :style="`font-size:18px;font-weight:400`">
             Priority health areas for FHS include HIV prevention, sexual and reproductive health and rights and malaria prevention. Currently, FHS is getting support from USAID, FCDO, KFW and Bill and Melinda Gates.
            </p>
            <nuxt-link to="/become-volunteer" class="join-one__btn thm-btn">
              <i class="fas fa-arrow-circle-right"></i>
              Learn More
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!--Join One End-->
</template>
<script>
export default {
  props: {
    className: {
      type: String,
    },
  },
};
</script>
