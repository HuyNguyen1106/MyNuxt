<template>
    <div>
        <v-navigation-drawer
            v-model="drawer"
            fixed
            app
        >
        <v-list>
            <v-list-item
                v-for="(item, i) in items"
                :key="i"
                :to="item.to"
                router
                exact
            >
            <v-list-item-action>
                <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
                <v-list-item-title v-text="item.title" />
            </v-list-item-content>
            </v-list-item>
        </v-list>
        </v-navigation-drawer>
        <v-app-bar
            fixed
            app
        >
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
        <v-toolbar-title v-text="title" />
        <v-spacer />
        
        </v-app-bar>
    </div>
</template>
<script>
export default {
    name: 'auth-header',
    data () {
        return {
            drawer: false,
            items: [
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
            title: 'Vuetify.js'
        }
    },
}
</script>