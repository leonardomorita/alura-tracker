<template>
    <div class="box has-text-weight-bold" :style="boxStyles">
        <slot></slot> <!-- Exibe todo o conteúdo que está dentro (elementos filhos) da tag <BoxComponent> -->
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BoxComponent',
    data() {
        return {
            boxStyles: {
                background: '#FAF0CA'
            }
        }
    }
});
</script>

