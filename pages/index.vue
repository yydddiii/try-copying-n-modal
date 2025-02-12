<template>
    <div class="main">
        {{ state }}
        <button @click="state = !state">Открыть попап</button>
        <button @click="state_s = !state_s">Открыть попап2</button>
    </div>
    <TestPopup/>
    <TestEss/>
</template>

<script setup>
const state = useState("state");
const state_s = useState("state_s");

</script>

<style>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
.main {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
</style>