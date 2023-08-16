<template>
    <div class="">
        <div class="py-8 px-10 mx-10">
            <div class="flex space-x-5 justify-center items-center font-light " role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input 
                type="text" 
                class="campoTarefa" 
                placeholder="Qual tarefa você deseja iniciar?"
                v-model="descricao"
                >
                <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import Temporizador from './Temporizador.vue';

export default defineComponent({
    name: 'FormulárioItem',
    emits: ['aoSalvarTarefa'],
    components: { 
        Temporizador 
    },
    data() {
        return{
            descricao: ''
        }
    },
    methods:{
        finalizarTarefa(tempoDecorrido: number) : void{
            this.$emit('aoSalvarTarefa', {
            duracaoEmSegundos: tempoDecorrido,
            descricao: this.descricao
            })
            this.descricao = ''
        }
    }
})
</script>

