<template>
  <v-app light>
    <default-header></default-header>
    <v-main>
      
        <nuxt />
      
    </v-main>
    <default-footer></default-footer>
  </v-app>
</template>

<script>
import DefaultHeader from '@/components/Header/Default'
import DefaultFooter from '@/components/Footer/Default'
export default {
  data () {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-table',
          title: 'Decks',
          to: '/decks'
        },
        {
          icon: 'mdi-account-box',
          title: 'Profile',
          to: '/profile'
        },
        {
          icon: 'mdi-settings',
          title: 'Settings',
          to: '/settings'
        }
      ],
      title: 'BrandNew'
    }
  },
  components: {
    DefaultHeader,
    DefaultFooter
  }
}
</script>
