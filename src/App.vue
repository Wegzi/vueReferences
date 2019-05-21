<template>
  <v-app>
    <v-container grid-list-md fluid>
      <v-layout row wrap>
        <v-flex xs4 offset-sm3>
          <AddTodo />
        </v-flex>
        <v-flex xs2>
          <FilterTodos />
        </v-flex>
      </v-layout>
    </v-container>
    <Todos/>
  </v-app>
</template>

<script>
import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
import FilterTodos from './components/FilterTodos.vue'

export default {
  name: 'app',
  components: {
    Todos,
    AddTodo,
    FilterTodos
  }
}
</script>
