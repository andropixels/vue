<template>
  <div id="services-page">
    <!-- Showcase -->
    <section class="services-showcase pb-40">
      <AppHero
        titleStyle="display-2 has-text-weight-bold mb-16"
        title="Services"
       
        :img="require('@/assets/about-us-5.png')"
        responsiveShowcase
      >
        <button
          slot="btn-content"
          class="btn navbar-item btn-rounded has-background-green is-borderless py-16 px-30"
        >
          <router-link to="/" class="has-text-darkgrey is-transitionless pr-4">
            <i class="fa fa-home"></i>
            Home
          </router-link>/
          <span class="has-text-white">Services</span>
        </button>
      </AppHero>
    </section>

    <!-- Features -->
    <section class="services-features">
      <div class="container">
        <AppHeadingTitle
         
        />
        <div class="columns is-multiline">
          <div class="column is-4" v-for="(card, i) in featuresCards" :key="i">
            <AppCard :card="card" hoverable />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import AppHero from "@/components/AppHero";
import AppHeadingTitle from "@/components/AppHeadingTitle";
import AppCard from "@/components/AppCard";

export default {
  name: "Services",
  components: {
    AppHero,
    AppHeadingTitle,
    AppCard
  },
  data() {
    return {
      featuresCards: [
        {
          img: require("@/assets/services-1.png"),
          
        },
        {
          img: require("@/assets/services-2.png"),
         
        },
        {
          img: require("@/assets/services-3.png"),
          
        },
        {
          img: require("@/assets/services-4.png"),
         
        },
        {
          img: require("@/assets/services-5.png"),
         
        },
        {
          img: require("@/assets/services-6.png"),
         
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
#services-page {
  position: relative;

  .services-features {
    padding-bottom: 100px;
  }
}
</style>
