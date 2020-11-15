<template>
    <v-card
        class="mx-3"
        max-width="650"
        hover
    >
        <v-list max-width="200">
            <v-list-item>
                <v-list-item-content>
                    <v-card-title>{{ name }}</v-card-title>
                    <v-card-subtitle>{{ description }}</v-card-subtitle>
                </v-list-item-content>
            </v-list-item>
        </v-list>
        <v-card-text>
            <v-list>
                <ul>
                    <li v-for="(amount, ingredient, index) in ingredients" :key="index">
                        {{ ingredient }}: {{ amount }}
                    </li>
                </ul>
            </v-list>
            <hr />
            <v-list>
                <ol>
                    <li v-for="step in steps" :key="step">{{ step }}</li>
                </ol>
            </v-list>
        </v-card-text>
    </v-card>
</template>
<script>
export default {
    name: 'Card',

    props: {
        id: String,
        author: String,
        name: String,
        ingredients: Object,
        steps: Array,
        cuisine: String,
        description: String,
        imageName: String
    }
}
</script>
<style>
    .v-card__text, .v-card__title {
        word-break: normal;
    }
</style>