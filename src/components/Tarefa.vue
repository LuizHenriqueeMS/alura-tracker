<template>
    <div class="box">
        <div class="columns">
            <div class="column is-7">
                <b>{{ tarefa.descricao }}</b>
            </div>
            <div class="column">
                <Cronometro :TempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

    import Cronometro from './Cronometro.vue';
    import ITarefa from '../interfaces/ITarefa';
    import { defineComponent , PropType } from 'vue';

    export default defineComponent({
        name:'MinhasTarefas',
        components:{
            Cronometro
        },
        props:{
            tarefa:{
                type: Object as PropType<ITarefa>,
                required : true
            }
        }
    })

</script>

<style scoped>
    .box{
        background : #FAF0CA;
    }
</style>