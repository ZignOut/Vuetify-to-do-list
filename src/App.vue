<template>
  <v-app>
    <div>
      <todo-toolbar></todo-toolbar>
    </div>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
import todoToolBarVue from "./components/todoToolBar.vue";
export default {
  name: "App",

  data: () => ({
    //
  }),

  components: {
    "todo-toolbar": todoToolBarVue
  }
};
</script>
