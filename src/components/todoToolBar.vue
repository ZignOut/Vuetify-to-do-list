<template>
  <v-toolbar>
    <v-toolbar-title>My Todo List</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-toolbar-items>
      <v-btn icon href="/">
        <v-icon>home</v-icon>
      </v-btn>

      <v-btn icon href="/about">
        <v-icon>info</v-icon>
      </v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
export default {
    name: 'todotoolbar'
};
</script>