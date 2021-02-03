<template>
    <div class="register">
        <v-col md="4">
            <v-card>
                <v-form lazy-validation>
                    <v-card-title>
                        Register panel
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
                        <v-btn large>Register</v-btn>
                    </v-card-actions>
                </v-form>
            </v-card>
        </v-col>
    </div>
</template>
<script>
export default {
    layout: 'empty',
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
}
</script>
<style lang="scss">
    .register {
        min-width: 100vw;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
    }
</style>