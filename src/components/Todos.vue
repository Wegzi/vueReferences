<template lang="html">
  <v-layout>

    <v-flex xs12 sm6 offset-sm3>
      <v-container grid-list-lg fluid>
        <v-layout row wrap>
          <v-flex xs3
            v-for="todo in allTodos"
            v-bind:key="todo.id"
            @dblclick="onDblClick(todo)"
          >
          <v-card v-bind:class="{'pink':todo.completed}" >
            <v-card-text>{{ todo.title }}</v-card-text>
            <v-card-actions>
              <v-btn flat icon color="dark"  @click="deleteTodo(todo.id)">
                <v-icon>delete</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>

        </v-layout>

      </v-container>

    </v-flex>
  </v-layout>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  name: "Todos",
  methods: {
    ...mapActions(['fetchTodos', 'deleteTodo', 'updateTodo']),
    onDblClick(todo){
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      }
      this.updateTodo(updTodo)
    }
  },
  computed: mapGetters(['allTodos']),
  created() {
    this.fetchTodos();
  }
}
</script>

<style lang="css" scoped>
.is-completed{
  background-color: red;
}

</style>
