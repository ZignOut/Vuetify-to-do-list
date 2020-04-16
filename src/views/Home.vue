<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="title">To Do</h1>
        <v-spacer></v-spacer>
        <todo-list :listsData="lists" @clicked="finishList" @added="addNewList"></todo-list>
      </v-col>

      <v-col>
        <todo-history :listData="lists"></todo-history>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import todoListVue from "../components/todoList.vue";
import todoHistoryVue from "../components/todoHistory.vue";
export default {
  name: "Home",

  components: {
    "todo-list": todoListVue,
    "todo-history": todoHistoryVue
  },

  data() {
    return {
      lists: [
        {
          title: "Play Game",
          completed: false,
          created_date: 0,
          finished_date: null
        },
        {
          title: "Sleep",
          completed: false,
          created_date: 0,
          finished_date: null
        },
        {
          title: "Eat",
          completed: false,
          created_date: 0,
          finished_date: null
        },
        {
          title: "Talk",
          completed: false,
          created_date: 0,
          finished_date: null
        },
        {
          title: "Code",
          completed: false,
          created_date: 0,
          finished_date: null
        },
        {
          title: "Design",
          completed: false,
          created_date: 0,
          finished_date: null
        }
      ]
    };
  },

  methods: {
    addNewList: function(title) {
      if (title != "") {
        let date = new Date();
        let localDate = date.toLocaleDateString();

        this.lists.push({
          title: title,
          completed: false,
          created_date: localDate,
          finished_date: null
        });
      }
    },
    finishList: function(title, status) {
      let date = new Date();
      let localDate = date.toLocaleDateString();

      let finished_list = this.lists.filter(list => list.title == title);

      finished_list[0].completed = status;
      finished_list[0].finished_date = localDate;
    }
  }
};
</script>
