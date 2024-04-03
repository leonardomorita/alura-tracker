<template>
    <div class="box has-text-weight-bold">
        <slot></slot> <!-- Exibe todo o conteúdo que está dentro (elementos filhos) da tag <BoxComponent> -->
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BoxComponent'
});
</script>

<style scoped>
.box {
    background: #FAF0CA;
}
</style>
