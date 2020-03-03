<template>
  <div>
      <h3>Todos</h3>
        <div v-for='todo in allTodos' :key='todo.id'>
            {{todo.title}}
            <button @click='deleteTodo(todo.id)'>X</button>
        </div>
  </div>
</template>

<script>
import {mapGetters,mapActions} from 'vuex'

export default {
    name: 'Todos',
    computed: mapGetters(['allTodos']),
    methods: {
        ...mapActions(['fetchTodos','deleteTodo'])
    },
    created(){
        this.fetchTodos()
    }
}
</script>

<style scoped>
.todos{ 
    display: grid;
    grid-template-columns: repeat(3,1fr);
    grid-gap: 1rem;
}

.todo {
    border: 1px solid #ccc;
    background: #41b883;
    padding: 1rem;
    border-radius: 5px;
    text-align: center;
    position: relative;
    cursor: pointer;
}

</style>