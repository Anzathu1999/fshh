<template>
  <div>
    <header class="main-header clearfix">
      <div class="main-header__logo">
        <nuxt-link to="/">
          <img :src="require(`~/assets/images${logo.light}`)" width="180" alt=""/>
        </nuxt-link>
      </div>
      <div class="main-menu-wrapper">
        <div class="main-menu-wrapper__top">
          <div class="main-menu-wrapper__top-inner">
            <div class="main-menu-wrapper__left">
              <div class="main-menu-wrapper__left-content">
                <div class="main-menu-wrapper__left-text">
                  <p>Family Health Services, Kanengo, Area 28 Plot 198, PO Box 30132, Capital City, Lilongwe 3, Malawi</p>
                </div>
             
              </div>
            </div>
            <div class="main-menu-wrapper__right">
              <div class="main-menu-wrapper__right-social">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
              </div>
            </div>
          </div>
        </div>
        <div class="main-menu-wrapper__bottom" :style="`background-image: url(${require(`~/assets/images/backgrounds/web_menu_bg.png`)});background-size: 200px;background-repeat: repeat-x;`">
          <nav class="main-menu custom-nav" >
            <div class="main-menu__inner">
              <a
                href="#"
                class="mobile-nav__toggler"
                @click="mobileDrawerStatusChange"
              >
                <i class="fa fa-bars"></i>
              </a>
        
              <ul class="main-menu__list">
                <li 
                  v-for="item in navMenus"
                  :key="item.name"
                  :class="`${undefined !== item.subItems ? 'dropdown ' : ' '}`"
                >
                  <nuxt-link :to="item.url">{{ item.name }}</nuxt-link>
                  <ul class="sub-menu" v-if="undefined !== item.subItems">
                    <li v-for="subitem in item.subItems" :key="subitem.name">
                      <nuxt-link :to="subitem.url">{{
                        subitem.name
                      }}</nuxt-link>
                      <ul
                        class="sub-menu"
                        v-if="undefined !== subitem.subItems"
                      >
                        <li
                          v-for="subitem in subitem.subItems"
                          :key="subitem.name"
                        >
                          <nuxt-link :to="subitem.url">{{
                            subitem.name
                          }}</nuxt-link>
                        </li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
              <div class="main-menu__right">
             
            
                <div class="main-menu__phone-contact">
                  <div class="main-menu__phone-icon">
                    <span class="icon-chat"></span>
                  </div>
                  <div class="main-menu__phone-number">
                    <p>Call Anytime</p>
                    <a href="tel:92 666 888 0000">92 666 888 0000</a>
                  </div>
                </div>
                <a href="#" class="main-menu__cart icon-shopping-cart"></a>
                <a
                  href="#"
                  class="main-menu__search search-toggler icon-magnifying-glass"
                  @click="searchPopupStatusChange"
                ></a>
              </div>
            </div>
          </nav>
        </div>
      </div>
    </header>

    <div
      :class="`stricky-header stricked-menu main-menu ${
        sticky ? 'stricky-fixed' : ''
      }`"
    >
      <div class="sticky-header__content">
        <div class="main-header__logon">
        <nuxt-link to="/">
          <img :src="require(`~/assets/images${logo.light}`)" width="120" alt=""/>
        </nuxt-link>
      </div>
        <div class="main-menu__inner">
          <a
            href="#"
            class="mobile-nav__toggler"
            @click="mobileDrawerStatusChange"
          >
            <i class="fa fa-bars"></i>
          </a>
          <ul class="main-menu__list">
            <li
              v-for="item in navMenus"
              :key="item.name"
              :class="`${undefined !== item.subItems ? 'dropdown ' : ' '}`"
            >
              <nuxt-link :to="item.url">{{ item.name }}</nuxt-link>
              <ul class="sub-menu" v-if="undefined !== item.subItems">
                <li v-for="subitem in item.subItems" :key="subitem.name">
                  <nuxt-link :to="subitem.url">{{ subitem.name }}</nuxt-link>
                  <ul class="sub-menu" v-if="undefined !== subitem.subItems">
                    <li v-for="subitem in subitem.subItems" :key="subitem.name">
                      <nuxt-link :to="subitem.url">{{
                        subitem.name
                      }}</nuxt-link>
                    </li>
                  </ul>
                </li>
              </ul>
            </li>
          </ul>
          <div class="main-menu__right">
            <a
              href="#"
              class="main-menu__search search-toggler icon-magnifying-glass"
              @click="searchPopupStatusChange"
            ></a>
            <a href="#" class="main-menu__cart icon-shopping-cart"></a>
            <div class="main-menu__phone-contact">
              <div class="main-menu__phone-icon">
                <span class="icon-chat"></span>
              </div>
              <div class="main-menu__phone-number">
                <p>Call Anytime</p>
                <a href="tel:92 666 888 0000">92 666 888 0000</a>
              </div>
            </div>
          
          </div>
        </div>
      </div>
      <!-- /.sticky-header__content -->
    </div>
    <!-- /.stricky-header -->
  </div>
</template>
<script>
import data from "~/data/data.json";
import { mapMutations } from "vuex";
export default {
  data() {
    return {
      currentPageURL: this.$route.path,
      logo: data.logo,
      navMenus: data.navMenus,
      sticky: false,
    };
  },
  computed: {
    mobileDrawer() {
      return this.$store.state.mobileDrawerStatus;
    },
    searchPopup() {
      return this.$store.state.searchPopupStatus;
    },
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
    ...mapMutations({
      mobileDrawerStatusChange: "changeMobileDrawerStatus",
      searchPopupStatusChange: "changeSearchPopupStatus",
    }),
  },
};
</script>
<style scoped>

.main-header__logon {
  position: relative;
  width: 17%;
  float: right;
  background-color: #fff;
  text-align: center;
  padding: 15px 0;
  
}

.main-menu-wrapper__top {

  background-color: #212494;
  
}
.main-menu-wrapper__left-text p {
  font-size: 12px;
  color: #fff;
  font-weight: 400;

}
.main-menu-wrapper__left-email-box .email a{
  color: #fff;
}
.fab {
margin: -20px;
color: white

}
.main-menu-wrapper__bottom{
  line-height: 10px;
}


</style>