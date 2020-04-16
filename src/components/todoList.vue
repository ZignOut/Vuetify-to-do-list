<template>
  <table>
    <tr v-for="list in lists.filter(doneList => doneList.completed==false)" :key="list">
      <td>{{ list.title }}</td>

      <td>
        <v-btn
          v-if="list.completed==false"
          depressed
          icon
          color="green"
          @click="finishList(list.title, true)"
        >
          <v-icon>done</v-icon>
        </v-btn>
      </td>

      <td>
        <v-btn
          v-if="list.completed==false"
          depressed
          icon
          color="red"
          @click="finishList(list.title, 'fail')"
        >
          <v-icon>schedule</v-icon>
        </v-btn>
      </td>
    </tr>

    <tr>
      <td>
        <v-textarea rows="1" prepend-icon="home" v-model="title"></v-textarea>
      </td>

      <td>
        <v-btn depressed icon @click="addNewList">
          <v-icon>mdi-plus</v-icon>
        </v-btn>
      </td>
    </tr>
  </table>
</template>

<script>
export default {
  name: "todo-list",

  props: ["listsData"],

  data() {
    return {
      title: "",
      lists: this.listsData
    };
  },

  methods: {
    finishList: function(title, status) {
      this.$emit("clicked", title, status);
    },
    addNewList: function() {
      this.$emit("added", this.title);
      this.title = "";
    }
  }
};
</script>