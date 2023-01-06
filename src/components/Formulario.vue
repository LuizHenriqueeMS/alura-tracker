<template>
    <div class="box">
        <div class="columns">
            <Temporizador/>
        </div>
    </div>
</template>

<script lang="ts">

    import { defineComponent } from 'vue';
    import Temporizador from './Temporizador.vue';

    export default defineComponent({
        name: "MeuFormulario",
        components:{
            Temporizador
        },
    })

</script>

<style>

</style>