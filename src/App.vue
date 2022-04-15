<template>
  <h1>{{ count }}</h1>

  <button @click="increment">incrementar</button>
  <button @click="decrease">Diminuir</button>
  <button @click="reset">Resetar</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment(): void {
      this.count++
    },
    decrease(): void {
      this.count--
    },
    reset(): void {
      this.count = 0
    }
  }
})
</script>
