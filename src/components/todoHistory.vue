<template>
  <div>
    <h2 class="title">History</h2>
    <v-list>
      <v-list-item v-for="list in lists.filter(item => item.completed!=false)" :key="list">
        <v-list-item-avatar v-if="list.completed==true">
          <v-icon class="green--text">mdi-check-circle-outline</v-icon>
        </v-list-item-avatar>

        <v-list-item-avatar v-else>
          <v-icon class="red--text">error</v-icon>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>{{ list.title }}</v-list-item-title>
          <v-list-item-subtitle>{{ list.finished_date }}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script>
export default {
  name: "todo-history",

  props: ["listData"],

  data() {
    return {
      lists: this.listData
    };
  }
};
</script>