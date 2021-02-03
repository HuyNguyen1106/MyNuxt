<template>
  <div>
    <v-app-bar>
      <v-tab to="/settings">General</v-tab>
      <v-tab to="/settings/deck">Deck</v-tab>
      <v-tab to="/settings/schedule">Schedule</v-tab>
    </v-app-bar>
    <v-container>
      <nuxt-child></nuxt-child>
    </v-container>
  </div>
</template>
<script>
export default {
  head() {
      return {
        title: "Settings"
      }
    },
}
</script>
