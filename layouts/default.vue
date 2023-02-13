<template>
  <v-app dark class="image_background">
    <v-row class="mt-2 px-2 row_top" justify="space-between">
      <v-col md="4">
        <v-img
          class="logo"
          max-width="37"
          max-height="32"
          src="/defultLayout/logo.png"
        ></v-img>
        <h1 class="logo_type mt-1 ml-12 white--text">MUON Explorer</h1>
      </v-col>
      <v-col md="5" class="text-right">
        <v-btn text class="navigation_btn px-2">Home</v-btn>
        <v-btn text class="navigation_btn px-2">Applications</v-btn>
        <v-btn text class="navigation_btn px-2">Requests</v-btn>
        <v-btn text class="navigation_btn px-2">Nodes</v-btn>
        <v-btn dark icon class="navigation_btn px-2"
          ><v-img max-width="40" src="/defultLayout/menuIcon.png"></v-img
        ></v-btn>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col md="10">
        <Nuxt />
      </v-col>
    </v-row>
    <v-footer color="gray">
      <v-row class="pa-2 mb-0" justify="space-between">
        <v-col md="2">
          <v-img
            class="logo"
            max-width="24"
            max-height="24"
            src="/defultLayout/logo.png"
          ></v-img>
          <span color="#F2F2F4" class="ml-2 gray2--text">By</span
          ><a class="ml-1 white--text" href="">Muon.Net</a>
        </v-col>
        <v-col md="3" class="text-right">
          <v-btn icon dark class="mx-2">
            <v-img
              width="34"
              height="27.5"
              src="/defultLayout/ic_discord.png"
            ></v-img>
          </v-btn>
          <v-btn icon dark class="mx-2">
            <v-icon class="text-h4">mdi-twitter</v-icon>
          </v-btn>
          <v-btn icon dark class="mx-2">
            <v-img
              width="36"
              height="36"
              src="/defultLayout/ic_telegram.png"
            ></v-img>
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
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 600;
  font-size: 24px;
  line-height: 29px;
}
.navigation_btn {
  font-family: 'Lato';
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 19px;

  color: #f9f9fa;
}
.row_top {
  flex: 0 !important;
}
</style>
