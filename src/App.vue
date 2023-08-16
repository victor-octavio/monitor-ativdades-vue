<template>
  <main class="bg-gray-900 w-screen h-screen"> 
    <h1 class="text-inherit text-5xl text-center py-5 font-semibold">
      
    </h1>
    <div class="">
      <BarraLateral/>
    </div>
    <div class="">
      <Formulario/>
    </div>
  </main>
   
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import Formulario from './components/Formulario.vue'
export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario
    
  }
});
</script>


