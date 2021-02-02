<template>
  <v-col cols="12" sm="4">
    <v-card class="mx-auto" max-width="400">
      <v-img
        class="white--text align-end"
        height="200px"
        v-bind:src="image"
      >
        <v-card-title>{{ title }}</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0"> {{ author }} </v-card-subtitle>

      <v-card-text class="text--primary">
        <div><slot></slot></div>
      </v-card-text>

      <v-card-actions>
        <v-btn color="orange" text v-bind:href="link" target="_blank"
          ><v-icon class="mr-3">mdi-alpha-c-circle</v-icon>Читать больше</v-btn
        >
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
    name: 'NewsItem',
    props:['image', 'link', 'title', 'author'],
};
</script>

<style>
</style>