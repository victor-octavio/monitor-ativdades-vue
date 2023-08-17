<template>
  <main class="bg-gray-900 w-screen h-screen"> 
    
    <div class="">
      <BarraLateral/>
    </div>
    <div>
      <Formulario @aoSalvarTarefa = "salvarTarefa"/>
      <div class="lista space-y-7">
        <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
      <TarefaVazia class="py-3" v-if="listaEstaVazia">
        Você não possui nenhuma tarefa em andamento!
      </TarefaVazia>
      </div>
    </div>
  </main>
   
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import Formulario from './components/Formulario.vue'
import Tarefa from './components/Tarefa.vue'
import ITarefa from './interfaces/ITarefa'
import TarefaVazia from './components/TarefaVazia.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario,
    Tarefa,
    TarefaVazia
  },
  data(){
    return {
      tarefas: [] as ITarefa[]
    }
  },
  computed: {
    listaEstaVazia() : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa){
      this.tarefas.push(tarefa)
    }
  }



});
</script>


