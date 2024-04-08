<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="" />
        </h1>

        <button class="button" @click="alterarTema">
            {{ textoBotao }}
        </button>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BarraLateral',
    emits: ['aoTemaAlterado'],
    data() {
        return {
            modoEscuro: false
        };
    },
    computed: {
        textoBotao() {
            if (this.modoEscuro) {
                return 'Desativar modo escuro';
            }

            return 'Ativar modo escuro';
        }
    },
    methods: {
        alterarTema() {
            this.modoEscuro = !this.modoEscuro;
            this.$emit('aoTemaAlterado', this.modoEscuro);
        }
    }
});
</script>

<style scoped>
header {
    background: #0D3B66;
    height: 100vh;
    padding: 1rem;
    text-align: center;
    width: 100%;
}

@media only screen and (max-width: 768px) {
    header {
        height: auto;
        padding: 2.5rem;
    }
}
</style>
