<template>
  <h1>{{ nomeCompleto }}</h1>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      nome: 'Blondie',
      sobrenome: 'Nami'
    }
  },
  computed: {
    nomeCompleto(): string {
      const nomeCompleto = `${this.nome} ${this.sobrenome}`
      return nomeCompleto
    }
  }
})
</script>
