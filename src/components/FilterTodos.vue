<template lang="html">
  <v-container grid-list-md>
    <v-layout row wrap>
      <v-flex offset-sm3>
        <h3>Filter</h3>
        <v-select :items="items" @change="filterTodos($event)">
        </v-select>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: "FilterTodos",
  data(){
    return{
      items: [200, 100, 50, 20, 10, 5]
    }
  },
  methods: mapActions(["filterTodos"])
}
</script>

<style lang="css" scoped>
</style>
