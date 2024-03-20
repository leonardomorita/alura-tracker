<template>
    <main class="columns is-gapless is-multiline">
        <div class="column is-one-quarter">
            <BarraLateral />
        </div>

        <div class="column is-three-quarter">
            <FormularioTarefas />
        </div>
    </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioTarefas from './components/FormularioTarefas.vue';

export default defineComponent({
    name: 'App',
    components: {
        BarraLateral,
        FormularioTarefas
    }
});
</script>

<style>
</style>
