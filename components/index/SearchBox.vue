<template>
  <v-text-field
    flat
    rounded
    height="60"
    background-color="white"
    class="main_search_box"
    label="Search by Address / Application Name / Node ID / Request ID"
  >
    <template v-slot:append>
      <div class="primaryLow mt-1 rounded-xl">
        <span v-if="true" class="primaryLight--text text_small mx-2"
          >Press Enter</span
        >
        <v-btn large icon color="primary" class="primary">
          <img
            width="20"
            src="@/static/components/serchBox/magnify.png"
            alt=""
          />
        </v-btn>
      </div>
    </template>
  </v-text-field>
</template>

<script>
export default {
  name: 'SearchBox',
}
</script>

<style scoped>
.text_small {
  font-size: 12px !important;
}
</style>
