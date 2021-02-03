<template>
  <v-app dark>
    <auth-header></auth-header>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <default-footer></default-footer>
  </v-app>
</template>

<script>
import AuthHeader from '@/components/Header/Auth'
import DefaultFooter from '@/components/Footer/Default'
export default {
  
  components: {
    AuthHeader,
    DefaultFooter
  }
}
</script>
