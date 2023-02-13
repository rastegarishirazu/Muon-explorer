<template>
  <v-text-field
    solo
    rounded
    class="main_search_box"
    label="Search by Address / Application Name / Node ID / Request ID"
  >
    <template v-slot:append>
      <v-btn icon color="primary" class="primary">
        <img width="20" src="@/static/components/serchBox/magnify.png" alt="" />
      </v-btn>
    </template>
  </v-text-field>
</template>

<script>
export default {
  name: 'SearchBox',
}
</script>
