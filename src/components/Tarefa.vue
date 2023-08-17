<template>
    <TarefaVazia>
        <div class="columns">
            <div class="column is-10">
                {{tarefa.descricao || "Tarefa sem descrição"}}
            </div>
            <div class="column py-1">
            <Cronometro :tempoEmSegundos = "tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </TarefaVazia>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Cronometro from './Cronometro.vue';
import ITarefa from '../interfaces/ITarefa';
import TarefaVazia from './TarefaVazia.vue';

export default defineComponent({
   name: 'TarefaItem',
   components: {
    Cronometro,
    TarefaVazia,
   },
   props: { 
    tarefa: {
        type: Object as PropType<ITarefa>,
        required: true
    }
   }

})
</script>
