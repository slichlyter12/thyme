<template>
    <v-card
        class="mx-3 d-block"
        max-width="344"
        hover
    >
        <v-list-item three-line>
            <v-list-item-content>
                <div class="overline mb-4">{{ duration }}</div>
                <v-list-item-title class="headline mb-1">{{ title }}</v-list-item-title>
                <v-list-item-subtitle>
                    <ul>
                        <li v-for="ingredient in ingredients" :key="ingredient">{{ ingredient }}</li>
                    </ul>
                </v-list-item-subtitle>
                <hr />
                <v-list-item-subtitle>
                    <ol>
                        <li v-for="step in steps" :key="step">{{ step }}</li>
                    </ol>
                </v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
    </v-card>
</template>
<script>
export default {
    name: 'Card',

    props: {
        id: Number,
        duration: String,
        title: String,
        ingredients: Array,
        steps: Array,
    }
}
</script>