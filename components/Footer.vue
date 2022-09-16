<template>
  <div>
    <!--Site Footer One Start-->
    <footer class="site-footer">
      <div
        class="site-footer-bg"
        :style="`background-image: url(${require(`~/assets/images/resources/patterns/pattern_img-bg.png`)}),url(${require(`~/assets/images/resources/patterns/pattern_wht-bg.png`)});background-position: right top, left bottom; background-size: 250px, 300px;`"
      ></div>
      <div class="container">
        <div class="site-footer__top">
          <div class="row" style="padding-left:100px;">
            <div class="col-xl-4 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__about">
                <h3 class="footer-widget__title">About</h3>
                <p class="footer-widget__text">
                  Family Health Services (FHS) formerly PSI/Malawi is a local organization implementing programs aimed at improving lives of Malawians.
                </p>
              </div>
            </div>
            <div class="col-xl-4 col-lg-6 col-md-6">
              <div
                class="footer-widget__column footer-widget__explore clearfix"
              >
                <h3 class="footer-widget__title">Explore</h3>
                <ul class="footer-widget__explore-list list-unstyled">
                  <li><a href="#">VMMC</a></li>
                  <li><a href="#">Sexual and Reproductive Health</a></li>
                  <li><a href="#">Covid-19</a></li>
                  <li><a href="#">HIV/AIDS</a></li>
                </ul>
                <!-- <ul
                  class="footer-widget__explore-list footer-widget__explore-list-two list-unstyled"
                >
                  <li><a href="#">Fundraising</a></li>
                  <li><a href="#">Contact</a></li>
                  <li><a href="#">Help</a></li>
                  <li><a href="#">Faqs</a></li>
                </ul> -->
              </div>
            </div>
            <div class="col-xl-4 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__contact">
                <h3 class="footer-widget__title">Contact</h3>
                <ul class="list-unstyled footer-widget__contact-list">
                  <li>
                    <div class="icon">
                      <i class="icon-chat"></i>
                    </div>
                    <div class="text">
                      <p>
                        <!-- <span>Call Anytime</span> -->
                        <a href="tel:265882009975">265 882009975</a>
                      </p>
                      <p>
                        <a href="tel:265992876775">265 992876775</a>
                      </p>
                    </div>
                  </li>
                  <li>
                    <div class="icon">
                      <i class="icon-message"></i>
                    </div>
                    <div class="text">
                      <p>
                        <!-- <span>Send Email</span> -->
                        <a href="mailto:needhelp@company.com"
                          >info@fhs.org.mw</a
                        >
                      </p>
                    </div>
                  </li>
                  <li>
                    <div class="icon">
                      <i class="icon-address"></i>
                    </div>
                    <div class="text">
                      <p>Family Health Services (FHS)</p><p> Head office and Main Warehouse,</p><p> Kanengo, Area 28 Plot 198,</p> <p>P.O.Box 30132, Capital City,</p><p>Lilongwe 3, Malawi</p>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
            <!-- <div class="col-xl-3 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__newsletter">
                <h3 class="footer-widget__title">Newsletter</h3>
                <p class="footer-widget__newsletter-text">
                  Lorem ipsum dolor sit ame consect etur pisicing elit sed do.
                </p>
                <form class="footer-widget__newsletter-form">
                  <input
                    type="email"
                    placeholder="Email address"
                    name="email"
                  />
                  <button type="submit" class="footer-widget__newsletter-btn">
                    <i class="fas fa-arrow-circle-right"></i>Send
                  </button>
                </form>
              </div>
            </div> -->
          </div>
        </div>
      </div>
    </footer>
    <!--Site Footer One End-->
    <div v-if="sticky === true">
      <a
        @click="scrollTop"
        class="scroll-to-target scroll-to-top animated fadeInUp"
        ><i class="fa fa-angle-up"></i
      ></a>
    </div>
    <SponsorsOne />
  </div>

</template>

<script>
import data from "~/data/data.json";
export default {
  data() {
    return {
      logo: data.logo,
      sticky: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 70) {
        this.sticky = true;
      } else if (window.scrollY < 70) {
        this.sticky = false;
      }
    },
    scrollTop() {
      window.scrollTo(0, 0);
    },
  },
};
</script>

<style scoped>
 /*--------------------------------------------------------------
# Site Footer
--------------------------------------------------------------*/
.site-footer {
  position: relative;
  display: block;
  padding: 40px 0 40px 0;
  background-color: #1f204c;
}

.site-footer-bg {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  filter: grayscale(0%);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: left bottom;
  opacity: 0.4;


}


</style>>
