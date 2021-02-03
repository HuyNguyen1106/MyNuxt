<template>
    <section>
        <h3>List of your decks:</h3>
        <v-row>
            <v-col sm="12" md="6" v-for="item in 3" :key="item">
                <v-card>
                    <v-card-title>Card title</v-card-title>
                    <v-card-subtitle>subtitle</v-card-subtitle>
                    <v-card-text
                        >Lorem ipsum dolor sit, amet consectetur adipisicing
                        elit. Deserunt asperiores enim, iusto error ea in fugiat
                        dolorum fugit corrupti delectus accusantium, dicta
                        laboriosam excepturi aliquid nulla soluta voluptate,
                        doloribus rem.</v-card-text
                    >
                    <v-card-actions>
                        <v-btn @click="showDeck(item)">Detail</v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </section>
</template>
<script>
export default {
    name: 'Decks',
    head() {
        return {
            title: 'Decks',
        }
    },
    methods: {
        showDeck(id) {
            this.$router.push(`/decks/${id}`)
        },
    },
}
</script>
