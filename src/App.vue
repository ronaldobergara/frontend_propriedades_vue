<template>
  <p v-for="todo in doneTodos" :key="todo.text">
    {{ todo.text }}
  </p>

  <button @click="checkAllTodos()">Finalizar</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

// [x] Definir o dado `todos`
// [x] Preencher os `todos` quando o componente é criado
// [x] Exibir em tela apenas `todos` concluídos
// [x] Ter um método para concluir os `todos`
// [x] Mostrar um alerta quando todos os `todos` forem finalizados

interface Todo {
  text: string
  done: boolean
}

export default defineComponent({
  data() {
    return {
      todos: [] as Todo[]
    }
  },
  created() {
    this.todos = [
      { text: 'Estudar Typescript', done: true },
      { text: 'Lavar os pratos', done: false },
      { text: 'Aprender Nuxt.js', done: true }
    ]
  },
  computed: {
    doneTodos(): Todo[] {
      return this.todos.filter((todo) => todo.done)
    }
  },
  watch: {
    todos(newValue: Todo[]) {
      const isFinished = !newValue.some(({ done }) => !done)

      if (isFinished) {
        alert('Yuuuuuuup')
      }
    }
  },
  methods: {
    checkAllTodos() {
      this.todos = this.todos.map(({ text }) => {
        return { text, done: true }
      })
    }
  }
})
</script>

<style>
p {
  font-size: larger;
  font-weight: bold;
  font-size: 50px;
}
</style>
