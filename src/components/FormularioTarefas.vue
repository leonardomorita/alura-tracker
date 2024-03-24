<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input
                    type="text"
                    class="input"
                    placeholder="Qual tarefa você deseja iniciar?"
                    v-model="descricao"
                >
            </div>

            <div class="column">
                <TemporizadorComponent @temporizador-finalizado="finalizarTarefa" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TemporizadorComponent from './TemporizadorComponent.vue';

export default defineComponent({
    name: 'FormularioTarefas',
    components: {
        TemporizadorComponent
    },
    data() {
        return {
            descricao: ''
        }
    },
    methods: {
        finalizarTarefa(tempoDecorrido: number): void {
            console.log(tempoDecorrido);
            console.log(this.descricao);
            this.descricao = '';
        }
    }
});
</script>
