<template>
    <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
            
            <Cronometro :TempoEmSegundos="TempoEmSegundos"/>
            
            <button class="button" @click="iniciar" :disabled="cronometroRodando">
                <span class="icon">
                    <i class="fas fa-play"></i>
                </span>
                <span>play</span>
            </button>
            <button class="button" @click="finalizar" :disabled="!cronometroRodando">
                <span class="icon">
                    <i class="fas fa-stop"></i>
                </span>
                <span>stop</span>
            </button>
            
        </div>
    </div>
</template>

<script lang="ts">

    import { defineComponent } from 'vue';
    import Cronometro from './Cronometro.vue';

    export default defineComponent({
        name: "MeuFormulario",
        emits:['aoTemporizadorFinalizado'],
        components:{
            Cronometro
        },
        data() {
            return {
                TempoEmSegundos: 0,
                cronometro: 0,
                cronometroRodando: false
            };
        },
        methods: {
            iniciar() {
                this.cronometro = setInterval(() => {
                    this.TempoEmSegundos += 1;
                }, 1000);

                this.cronometroRodando = true;
            },
            finalizar() {
                clearInterval(this.cronometro);
                this.cronometroRodando = false;
                this.$emit('aoTemporizadorFinalizado', this.TempoEmSegundos);
                this.TempoEmSegundos = 0;
            }
        }
    })

</script>