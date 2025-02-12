<template>
    <popup-new title="esss" v-model:show="state">
        <h1>Првиет</h1>
        <button @click="state_s = true">Получилось</button>
    </popup-new>
</template>

<script setup>
const state = useState("state");
const state_s = useState("state_s");
</script>

<style></style>
