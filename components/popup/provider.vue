<template>
    <div class="popup-provider">
        <slot />
        <div id="popup-provider-container"></div>
    </div>
</template>

<script setup></script>

<style>
#popup-provider-container {
    position: fixed;
    z-index: 1000;
}
</style>
