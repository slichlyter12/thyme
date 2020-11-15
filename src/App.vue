<template>
  <v-app>
    <div id="bg" :style="{'background-image': `url(${require('@/assets/croissant.jpg')})`}">
      <v-app-bar
        dark
        dense
        absolute
        elevate-on-scroll
        scroll-target="#content"
        color="rgba(0,0,0,0.3)"
      >
        <v-toolbar-title>Thyme: Save some time</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon><v-icon>mdi-plus</v-icon></v-btn>
      </v-app-bar>
      <v-content id="content">
          <Card class="d-inline-flex my-3" v-for="recipe in recipes" :key="recipe.id" v-bind="recipe"></Card>
      </v-content>
    </div>
  </v-app>
</template>

<script>
import Card from './components/Card';

export default {
  name: 'App',

  components: {
    Card,
  },

  data: () => ({
    recipes: []
  }),

  created() {
    // let headers = {"Access-Control-Allow-Origin": "true"}
    fetch("http://localhost:8080/api/recipe")
    .then(response => response.json())
    .then(data => (this.recipes = data));
  }
}
</script>
<style>
  #bg {
    height: 100%;
    width: auto;
    background-attachment: fixed; 
    background-size: cover;
  }

  #content {
    margin-top: 50px;
  }
</style>