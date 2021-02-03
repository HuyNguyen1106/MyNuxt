<template>
    <div class="login">
        <v-col sm="12" md="4">
            <v-card>
                <v-form lazy-validation ref="form" v-model="valid" @submit.prevent="signIn">
                    <v-card-title>
                        Login Panel
                    </v-card-title>
                    <v-card-text>
                        <v-text-field
                            label="ID"
                            :rules="idRules"
                            outlined
                            autofocus
                        >
                        </v-text-field>
                        <v-text-field
                            label="Password"
                            :rules="passRules"
                            outlined
                            type="password"
                        >
                        </v-text-field>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn large type="submit">Login</v-btn>
                    </v-card-actions>
                </v-form>
            </v-card>
        </v-col>
    </div>
</template>
<script>
export default {
    layout: 'empty',
    data() {
        return {
            valid: true,
        }
    },
    computed: {
        idRules() {
            return [
                v => !!v || "ID is required",
                v => (v && v.length >= 5) || "ID must be at least 5 characters"
            ]
        },
        passRules() {
            return [
                v => !!v || "Password is required",
                v => (v && v.length >= 5) || "Password must be at least 5 characters"
            ]
        }
    },
    methods: {
        validate() {
            return this.$refs.form.validate()
        },
        signIn() {
            if(this.validate()) {
                this.$router.push("/decks")
            }
        }
    }
}
</script>
<style lang="scss">
    .login {
        min-width: 100vw;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
    }
</style>