<template>
    <button class="button" @click="clicado" :disabled="desabilitado">
        <span class="icon">
            <i :class="['fas', icone]"></i>
        </span>

        <span>{{ textoBotao }}</span>
    </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BotaoComponent',
    emits: ['clicado'],
    props: {
        desabilitado: {
            type: Boolean
        },
        icone: {
            type: String,
            required: true
        },
        textoBotao: {
            type: String,
            required: true
        }
    },
    methods: {
        clicado(): void {
            this.$emit('clicado');
        }
    }
});
</script>
