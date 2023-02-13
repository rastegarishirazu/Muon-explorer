<template>
  <div>
    <v-row>
      <v-col>
        <SearchBox></SearchBox>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <MuonRequestsHistory></MuonRequestsHistory>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import MuonRequestsHistory from '~/components/index/MuonRequestsHistory.vue'
import SearchBox from '~/components/index/SearchBox.vue'

export default {
  name: 'IndexPage',
  components: { SearchBox, MuonRequestsHistory },
  data() {
    return {
      theme: true,
    }
  },
  methods: {
    changeTheme() {
      this.theme = !this.theme
      this.$vuetify.theme.dark = this.theme
    },
  },
}
</script>
