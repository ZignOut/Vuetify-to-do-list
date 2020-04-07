<template>
  <v-app>
    <div>
      <v-toolbar>
        <v-toolbar-title>My Todo List</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items>
          <v-btn icon>
            <v-icon>mdi-facebook</v-icon>
          </v-btn>

          <v-btn icon>
            <v-icon>mdi-instagram</v-icon>
          </v-btn>

          <v-btn icon>
            <v-icon>mdi-github</v-icon>
          </v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </div>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  })
};
</script>
