<template lang="html">
  <div>
    <form>
      <h3>Add Todo</h3>
      <v-container grid-list-md mx-0 px-0>
        <v-layout row wrap>
          <v-flex>
            <v-text-field v-model="title" label="Title"></v-text-field>
          </v-flex>
          <v-flex xs2  >
            <v-btn @click="onSubmit">submit</v-btn>
          </v-flex>
        </v-layout>
      </v-container>
    </form>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    ...mapActions(['addTodo']),
    onSubmit(e) {
      e.preventDefault()
      this.addTodo(this.title)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
