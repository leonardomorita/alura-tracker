<template>
    <BoxComponent>
        <div class="columns">
            <div class="column is-7">{{  tarefa.descricao || 'Tarefa sem descrição'  }}</div>

            <div class="column">
                <CronometroComponent :tempo-em-segundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </BoxComponent>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import BoxComponent from './BoxComponent.vue';
import CronometroComponent from './CronometroComponent.vue';
import ITarefa from '@/interfaces/ITarefa';

export default defineComponent({
    name: 'TarefaComponent',
    components: {
        BoxComponent,
        CronometroComponent
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>
