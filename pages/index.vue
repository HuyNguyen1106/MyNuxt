<template>
    <div>
        <v-carousel
            cycle
            height="400"
            hide-delimiter-background
            show-arrows-on-hover
        >
            <v-carousel-item v-for="(slide, i) in slides" :key="i">
                <v-sheet :color="colors[i]" height="100%">
                    <v-row class="fill-height" align="center" justify="center">
                        <div class="display-3">{{ slide }} Slide</div>
                    </v-row>
                </v-sheet>
            </v-carousel-item>
        </v-carousel>
        <v-container>
            <h1>Popular Decks</h1>
            <v-row>
                <v-col sm="12" md="4" v-for="item in 3" :key="item">
                    <popular-card></popular-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import PopularCard from "@/components/Card/PopularCard"
export default {
    layout: 'public',
    components: {
      PopularCard
    },
    head() {
      return {
        title: "Home"
      }
    },
    data() {
        return {
            colors: [
                'indigo',
                'warning',
                'pink darken-2',
                'red lighten-1',
                'deep-purple accent-4',
            ],
            slides: ['First', 'Second', 'Third', 'Fourth', 'Fifth'],
            show: false,
        }
    },
}
</script>
