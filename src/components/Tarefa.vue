<template>
    <div class="container w-3/5 shadow-md font-bold shadow-black h-12 text-white bg-gray-950 px-5">
        <div class="columns">
            <div class="column is-10">
                {{tarefa.descricao}}
            </div>
            <div class="column py-1">
            <Cronometro :tempoEmSegundos = "tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Cronometro from './Cronometro.vue';
import ITarefa from '../interfaces/ITarefa';

export default defineComponent({
   name: 'TarefaItem',
   components: {
    Cronometro,
   },
   props: { 
    tarefa: {
        type: Object as PropType<ITarefa>,
        required: true
    }
   }

})
</script>
