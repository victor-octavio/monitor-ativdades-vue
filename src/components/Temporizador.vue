<template>
	<div class="flex space-x-6">
		<Cronometro :tempoEmSegundos="tempoEmSegundos"/>
		<button class="botao" @click="iniciar" :disabled="cronometroRodando">
			<span class="icon">
				<i class="fas fa-play "></i>
			</span>
			<span>play</span>
		</button>
		<button class="botao" @click = "finalizar" :disabled="!cronometroRodando">
			<span class="icon">
				<i class="fas fa-stop"></i>
			</span>
			<span>stop</span>
		</button>
	</div>
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import Cronometro from './Cronometro.vue'

export default defineComponent({
	name: 'TemporizadorItem',
	emits: [
		'aoTemporizadorFinalizado'
	],
	data(){
        return{
            tempoEmSegundos: 0,
            cronometro: 0,
			cronometroRodando: false,
			
        }
    },
	components:{
        Cronometro
    },
	methods: {
        // Começar a contagem
        iniciar(){
		this.cronometroRodando = true
        this.cronometro = setInterval(() => {
            this.tempoEmSegundos += 1
            }, 1000)
        },
        // Finalizar a contagem
        finalizar(){
			this.cronometroRodando = false
            clearInterval(this.cronometro)
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
			this.tempoEmSegundos = 0
        }
    }
	
})
</script>

