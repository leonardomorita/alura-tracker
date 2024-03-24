<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <CronometroComponent :tempoEmSegundos="tempoEmSegundos" />

        <BotaoComponent
            @clicado="iniciar"
            :desabilitado="cronometroRodando"
            icone="fa-play"
            textoBotao="Play"
        />

        <BotaoComponent
            @clicado="finalizar"
            :desabilitado="!cronometroRodando"
            icone="fa-stop"
            textoBotao="Stop"
        />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BotaoComponent from './BotaoComponent.vue';
import CronometroComponent from './CronometroComponent.vue';

export default defineComponent({
    name: 'TemporizadorComponent',
    components: {
        BotaoComponent,
        CronometroComponent
    },
    emits: [
        'temporizadorFinalizado'
    ],
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    methods: {
        iniciar() {
            this.cronometroRodando = true;

            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        finalizar() {
            this.cronometroRodando = false;
            
            clearInterval(this.cronometro);

            this.$emit('temporizadorFinalizado', this.tempoEmSegundos);
            this.tempoEmSegundos = 0;
        }
    }
});
</script>
