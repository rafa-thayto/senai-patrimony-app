<template>
  <v-toolbar dark color="primary" flat extended>
    <v-toolbar-side-icon></v-toolbar-side-icon>
    <v-toolbar-title>{{ title }}</v-toolbar-title>
    <v-spacer></v-spacer>
  </v-toolbar>
</template>

<script>
export default {
  name: 'header',
  props: {
    title: String
  }
}
</script>

<style>

</style>
