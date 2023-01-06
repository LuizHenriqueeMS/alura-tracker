<template>
    <section>
        <strong>
            {{ TempoDecorrido }}
        </strong>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'MeuCronometro',
        props:{
            TempoEmSegundos : {
                type: Number,
                default: 0
            }
        }
        ,
        computed:{
            TempoDecorrido() : string { 
                return new Date(this.TempoEmSegundos * 1000).toISOString().substr(11,8)
            }
        }
        
    })
</script>