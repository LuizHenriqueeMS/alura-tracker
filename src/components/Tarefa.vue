<template>
    <div class="box">
        <div class="columns">
            <div class="column is-7">
                descricao da Tarefa
            </div>
            <div class="column">
                <Cronometro :TempoEmSegundos="15"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

    import Cronometro from './Cronometro.vue';
    import { defineComponent } from 'vue';

    export default defineComponent({
        name:'MinhasTarefas',
        components:{
            Cronometro
        }
    })

</script>

<style scoped>
    .box{
        background : #FAF0CA;
    }
</style>