<template>
  <v-container>
    <v-row>
      <v-col>
        <h1 class="title">To Do</h1>

        <table>
          <h2>Incompleted</h2>
          <tr v-for="list in lists.filter(doneList => doneList.completed==false)" :key="list">
            <td>{{ list.title }}</td>

            <td>
              <v-btn
                v-if="!list.completed"
                depressed
                icon
                color="green"
                @click="list.completed=!list.completed"
              >
                <v-icon>done</v-icon>
              </v-btn>

              <v-btn v-else depressed icon color="red" @click="list.completed=!list.completed">
                <v-icon>remove</v-icon>
              </v-btn>
            </td>
          </tr>

          <tr>
            <td>
              <v-textarea rows="1" prepend-icon="home" @addingList="addingList"></v-textarea>
            </td>

            <td>
              <v-btn depressed icon @click="$emit('addingList')">
                <v-icon>mdi-plus</v-icon>
              </v-btn>
            </td>
          </tr>

          <h2>Completed</h2>

          <tr v-for="list in lists.filter(doneList => doneList.completed==true)" :key="list">
            <td>{{ list.title }}</td>

            <td>
              <v-btn
                v-if="!list.completed"
                depressed
                icon
                color="green"
                @click="list.completed=!list.completed"
              >
                <v-icon>done</v-icon>
              </v-btn>

              <v-btn v-else depressed icon color="red" @click="list.completed=!list.completed">
                <v-icon>remove</v-icon>
              </v-btn>
            </td>
          </tr>
        </table>
      </v-col>
    </v-row>

    <v-row></v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      newTitle: { title: "", completed: false },
      lists: [
        { title: "Play Game", completed: false },
        { title: "Sleep", completed: false },
        { title: "Eat", completed: false },
        { title: "Talk", completed: false },
        { title: "Code", completed: false },
        { title: "Design", completed: false }
      ]
    };
  },

  methods: {
    addNewList: function(e) {
      this.newTitle.title = e.target.value;
      this.lists.push(this.newTitle);
    }
  }
};
</script>
