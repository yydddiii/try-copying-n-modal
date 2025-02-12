<template>
    <Teleport to="#popup-provider-container" v-if="is_mounted">
        <Transition name="popup-fade">
            <div v-if="show" class="popup-new">
                <div class="popup-new-bg" @click="closePopupBG">
                    <div class="popup-new-body" @click.stop>
                        <slot />
                    </div>
                </div>
            </div>
        </Transition>
    </Teleport>
</template>

<script setup>
const props = defineProps({
    bg_close: {
        type: Boolean,
        default: true,
    },
    esc_close: {
        type: Boolean,
        default: true,
    },
});

const emit = defineEmits(["update:show"]);

const show = defineModel("show");

const is_mounted = ref(false);

onMounted(() => {
    is_mounted.value = true;
});

const closePopupBG = () => {
    if (props.bg_close) emit("update:show", false);
};
</script>

<style>
.popup-new {
    position: fixed;
    inset: 0;
}

.popup-new-bg {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.5);
}

.popup-new-body {
    background: white;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.popup-fade-enter-active,
.popup-fade-leave-active {
    transition: opacity 0.3s;
}

.popup-fade-enter-from,
.popup-fade-leave-to {
    opacity: 0;
}
</style>
