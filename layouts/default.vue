<template>
  <v-app class="all_bg">
    <v-row class="mt-2 px-8 row_top" justify="space-between">
      <v-col md="4">
        <v-img
          class="logo"
          max-width="37"
          max-height="32"
          src="/defultLayout/logo.svg"
        ></v-img>
        <h1 class="logo_type ml-12 primary--text">
          MUON <br />
          Explorer
        </h1>
      </v-col>
      <v-col md="5" class="text-right white--text">
        <v-btn text class="navigation_btn gray2--text px-2">Home</v-btn>
        <v-btn text class="navigation_btn px-2">Applications</v-btn>
        <v-btn text class="navigation_btn px-2">Requests</v-btn>
        <v-btn text class="navigation_btn px-2">Nodes</v-btn>
        <v-btn
          icon
          elevation="0"
          class="navigation_btn rounded-lg primaryLow px-2"
        >
          <v-icon color="primaryLight">mdi-menu</v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col md="10">
        <Nuxt />
      </v-col>
    </v-row>
    <v-footer padless color="all_bg ">
      <v-row class="pa-2 mb-0">
        <v-col offset="5" md="2" class="" align-self="center">
          <v-img
            class="logo"
            max-width="24"
            max-height="24"
            src="/defultLayout/logo.svg"
          ></v-img>
          <span color="#F2F2F4" class="gray2--text ml-2">By</span
          ><a
            class="ml-1 gray1--text text-decoration-none font-weight-bold"
            href=""
            >Muon.Net</a
          >
        </v-col>
        <v-col md="5" class="text-right">
          <v-btn icon dark class="mx-4">
            <v-img
              width="34"
              height="27.5"
              src="/defultLayout/ic_discord.svg"
            ></v-img>
          </v-btn>
          <v-btn icon dark class="mx-4">
            <v-img
              width="34"
              height="27.5"
              src="/defultLayout/ic_twitter.svg"
            ></v-img>
          </v-btn>
          <v-btn icon dark class="mx-4">
            <v-img
              width="36"
              height="36"
              src="/defultLayout/ic_telegram.svg"
            ></v-img>
          </v-btn>
          <v-btn icon class="mx-4">
            <v-img src="/defultLayout/ic_other.svg"></v-img>
          </v-btn>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script>

<style scoped>
/* @import url('@/assets/fonts.scss'); */
.image_background {
  background: url('@/static/header.svg');
  background-repeat: no-repeat;
  background-size: contain;
  background-color: #eff0f5;
}
.logo {
  float: left;
}
.logo_type {
  font-style: normal;
  font-weight: 600;
  font-size: 14px;
  line-height: 15px;
}
.navigation_btn {
  font-family: 'Lato';
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 19px;
}
.row_top {
  flex: 0 !important;
}
.all_bg {
  background: #eff0f5;
}
</style>
