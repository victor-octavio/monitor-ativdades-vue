<template>
    <div class="container w-3/5 shadow-md font-bold shadow-black h-12 text-white bg-gray-950 px-5">
         <slot></slot>
    </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    name: 'TarefaVazia'
})
</script>

<style scoped>

</style>