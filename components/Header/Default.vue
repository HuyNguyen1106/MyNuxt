<template>
    <v-app-bar
      fixed
      app
      flat
    >
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn text to="/login">
        Login
      </v-btn>
      <v-btn text to="/register">
        Register
      </v-btn>
    </v-app-bar>
</template>
<script>
export default {
    name: 'default-header',
    data() {
        return {
            title: 'BrandNew'
        }
    },
}
</script>