<template lang="html">
  <v-layout >
    <v-flex offset-sm3>
      <v-container pb-0 mb-0 grid-list-lg fluid>
      <h3>Add Todo</h3>
        <v-layout>
            <form>
              <v-container>
                <v-layout>
                  <v-flex xs12 md8>
                    <v-text-field v-model="title" label="Title"></v-text-field>
                  </v-flex>
                  <v-flex xs12 md4 >
                    <v-btn @click="onSubmit">submit</v-btn>
                  </v-flex>
                </v-layout>
              </v-container>
            </form>
        </v-layout>
      </v-container>
    </v-flex>
  </v-layout>
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
