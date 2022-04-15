<template>
  <h1>{{ mensagem }}</h1>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      mensagem: 'Hello World!'
    }
  }
})
</script>
