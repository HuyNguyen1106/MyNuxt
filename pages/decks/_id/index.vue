<template>
    <section>
        <v-row>
            <v-col>
                <v-btn color="secondary" @click.prevent="$router.go(-1)"
                    >back</v-btn
                >
            </v-col>
        </v-row>
        <v-row>
            <v-col
                ><h1>
                    <v-badge tile inline left :content="deckInfo.id">{{
                        deckInfo.title
                    }}</v-badge>
                </h1></v-col
            >
        </v-row>
        <v-row>
            <v-col>
                <v-btn color="success">Start Now</v-btn>
                <v-btn color="info">Create a card</v-btn>
            </v-col>
        </v-row>
        <v-row>
            <v-col sm="12" md="6">
                <v-card class="mb-2" v-for="item in 6" :key="item">
                    <v-card-title>Card</v-card-title>
                    <v-card-subtitle>subtitle</v-card-subtitle>
                    <v-card-actions>
                        <v-btn color="secondary" right absolute>begin</v-btn>
                    </v-card-actions>
                    <br />
                </v-card>
            </v-col>
            <v-col sm="12" md="6" order-sm="first" order-md="last">
                <v-sheet color="white" elevation="1" rounded class="pa-4">
                    <p v-text="deckInfo.description"></p>
                </v-sheet>
            </v-col>
        </v-row>
    </section>
</template>
<script>
export default {
    validate({ params }) {
        return /^[0-9]$/.test(params.id)
    },
    data() {
        return {
            deckInfo: {
                id: 1,
                title: '',
                description: '',
            },
        }
    },
    head() {
        return {
            title: this.deckInfo.title,
        }
    },
    created() {
        this.deckInfo.id = this.$route.params.id
        this.deckInfo.title = `Deck ${this.$route.params.id} title`
        this.deckInfo.description =
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur provident eius, natus at porro quod labore mollitia odit, hic iusto ea. At esse maiores, voluptatum magni debitis eos. Voluptatem, sapiente.Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur provident eius, natus at porro quod labore mollitia odit, hic iusto ea. At esse maiores, voluptatum magni debitis eos. Voluptatem, sapiente.Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur provident eius, natus at porro quod labore mollitia odit, hic iusto ea. At esse maiores, voluptatum magni debitis eos. Voluptatem, sapiente.'
    },
}
</script>
<style lang="scss"></style>
