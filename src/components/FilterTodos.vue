<template>
  <div>Filter Todos  
    <select @change='filter($event)'>
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="20">20</option>
      <option value="10">10</option>
  </select>
  </div>

</template>

<script>

import {mapActions} from 'vuex'

export default {
  name: 'FilterTodos',
  methods: {
    ...mapActions(['filterTodos']),
    filter(e){
      const limit = parseInt(e.target.selectedOptions[0].value)
      this.filterTodos(limit)
    }  
  }

}
</script>

<style>

</style>