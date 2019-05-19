<template lang="html">
  <v-layout>
    <v-flex offset-sm3>
      <v-container  pt-0 mt-0 grid-list-lg fluid>
        <h3>Filter</h3>
        <v-layout row wrap>
          <v-flex xs3 md3 >
            <v-select @change="filterTodos($event)">
              <option value="200">200</option>
              <option value="100">100</option>
              <option value="50">50</option>
              <option value="20">20</option>
              <option value="10">10</option>
              <option value="5">5</option>
            </v-select>
          </v-flex>
        </v-layout>
      </v-container>
    </v-flex>
  </v-layout>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos"])
}
</script>

<style lang="css" scoped>
</style>
