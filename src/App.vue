<template>
    <main class="columns is-gapless is-multiline">
        <div class="column is-one-quarter">
            <BarraLateral />
        </div>

        <div class="column is-three-quarter">
            <FormularioTarefas @salvar-tarefa="salvarTarefa" />

            <div class="lista">
                <TarefaComponent v-for="(tarefa, index) in tarefas"
                    :key="index"
                    :tarefa="tarefa"
                />

                <BoxComponent v-if="listaVazia">Nenhuma tarefa no momento</BoxComponent>
            </div>
        </div>
    </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import BoxComponent from './components/BoxComponent.vue';
import FormularioTarefas from './components/FormularioTarefas.vue';
import TarefaComponent from './components/TarefaComponent.vue';
import ITarefa from './interfaces/ITarefa';

export default defineComponent({
    name: 'App',
    components: {
        BarraLateral,
        BoxComponent,
        FormularioTarefas,
        TarefaComponent
    },
    data() {
        return {
            tarefas: [] as ITarefa[]
        }
    },
    computed: {
        listaVazia(): boolean {
            return this.tarefas.length === 0;
        }
    },
    methods: {
        salvarTarefa(tarefa: ITarefa): void {
            this.tarefas.push(tarefa);
            console.log("Tarefa", tarefa);
        }
    }
});
</script>

<style>
.lista {
    padding: 1.25rem;
}
</style>
