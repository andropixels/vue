<template>
  <div id="about-page">
    <!-- Showcase -->
    <section class="about-showcase pb-40">
      <AppHero
        titleStyle="display-2 has-text-weight-bold mb-16"
        title="About Us"
        text="We are passionated towards making education free for all."
        :img="require('@/assets/page-about-img1.png')"
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
          <span class="has-text-white">About Us</span>
        </button>
      </AppHero>
    </section>

    <!-- About Us -->
    <section class="about-us-1 pb-40">
      <AppHero
        topTitleStyle="display-5 has-text-weight-medium"
        topTitle="About Us"
        titleStyle="display-3 has-text-weight-bold mb-16"
        title="TEAM DEVELOPERS"
        text=""
        :img="require('@/assets/page-about-img2.png')"
        row-reverse
      >
        <span slot="btn-content"></span>
      </AppHero>
    </section>

    <!-- About Us 2 -->
    <section class="about-us-2 pb-50">
      <AppTabs tabStyle="mb-24">
        <div class="container px-50">
          <AppTab :name="tab.name" v-for="tab in tabs" :key="tab.name">
            <AppHero
              paddingless
              topTitleStyle="display-5 has-text-weight-medium"
              :topTitle="tab.toptitle"
              titleStyle="display-3 has-text-weight-bold mb-16"
              :title="tab.title"
              text=""
              :img="tab.img"
              :row-reverse="tab.reverseRow"
            >
              <span slot="btn-content"></span>
            </AppHero>
          </AppTab>
        </div>
      </AppTabs>
    </section>

    <!-- Team -->
    <section class="about-team pt-30 pb-50">
      <div class="container px-50">
        <AppHeadingTitle title="Our Team" />
        <div class="columns">
          <div class="column is-3" v-for="(team, i) of teamCards" :key="i">
            <AppImageCard
              styles="is-shadowless"
              :img="team.img"
              :title="team.title"
             
            >
              <template slot="icon-content">
                <!-- AppIcon -->
                <AppIcon :icons="socialIcons" fab>
                  <template v-slot:icon="{ icon }">
                    <a :href="icon.href" class="has-text-green">
                      <i :class="icon.name"></i>
                    </a>
                  </template>
                </AppIcon>
              </template>
            </AppImageCard>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Clients -->
    <section class="about-clients pt-30">
      <div class="container">
        <AppHeadingTitle title="TEAM DEVELOPERS" />
        <AppSlider :img="clients">
          <template v-slot:item="{ item }">
            <img :src="item.img" :title="item.name" />
          </template>
        </AppSlider>
      </div>
    </section>
  </div>
</template>

<script>
import AppHero from "../components/AppHero";
import AppTabs from "../components/AppTabs";
import AppTab from "../components/AppTab";
import AppImageCard from "../components/AppImageCard";
import AppIcon from "@/components/AppIcon";
import AppHeadingTitle from "@/components/AppHeadingTitle";
import AppSlider from "@/components/AppSlider";

export default {
  name: "About",
  components: {
    AppHero,
    AppTabs,
    AppTab,
    AppImageCard,
    AppIcon,
    AppHeadingTitle,
    AppSlider
  },
  data() {
    return {
      tabs: [
        {
          name: "Financial",
          reverseRow: false,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-1.png")
        },
        {
          name: "Commercial",
          reverseRow: true,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-2.png")
        },
        {
          name: "Safety",
          reverseRow: false,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-3.png")
        },
        {
          name: "Transport",
          reverseRow: true,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-4.png")
        },
        {
          name: "Government",
          reverseRow: false,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-5.png")
        },
        {
          name: "Other",
          reverseRow: true,
          toptitle: "",
          title: "",
          text:
            "",
          img: require("@/assets/about-us-6.png")
        }
      ],

      // Team
      teamCards: [
        {
          img: require("@/assets/team-1.jpg"),
          title: "Rahul  Navgire",
          subtitle: "Web Developer"
        },
        {
          img: require("@/assets/team-2.jpg"),
          title: "pragati ",
          subtitle: "Web Designer"
        },
        {
          img: require("@/assets/team-3.jpg"),
          title: "apeyksha ",
          subtitle: "Market Expert"
        },
        {
          img: require("@/assets/team-4.jpg"),
          title: "Rahul Sagar",
          subtitle: "SEO Expert"
        }
      ],

      socialIcons: [
        { name: "fab fa-facebook-f", href: "#!" },
        { name: "fab fa-twitter", href: "#!" },
        { name: "fab fa-google", href: "#!" },
        { name: "fab fa-github", href: "#!" }
      ],

      // Clients
      clients: [
        { img: require("@/assets/clients-img1.png"), name: "HTML5" },
        { img: require("@/assets/clients-img5.png"), name: "Adobe Xd" },
        { img: require("@/assets/clients-img6.png"), name: "Bulma" },
        { img: require("@/assets/clients-img4.png"), name: "Vue" },
        { img: require("@/assets/clients-img2.png"), name: "CSS3" },
        { img: require("@/assets/clients-img3.png"), name: "Vuetify" }
      ]
    };
  }
};
</script>

<style lang="scss">
#about-page {
  position: relative;

  .about-us {
    &-2 {
      .btn:hover {
        color: #fff;
        background-image: $linear-bg;
      }
    }
  }

  .about-clients {
    padding-bottom: 100px;
    img {
      width: auto;
      margin: 0 auto;
    }
  }
}
</style>
