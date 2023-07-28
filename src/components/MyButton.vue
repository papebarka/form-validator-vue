<script>
    export default {
        props: {
            background: {
                type: String
            },
            color: {
                type: String
            },
            disabled: {
                type: Boolean,
            }
        }
    }
</script>

<template>
    <button
    :style="{ background, color }"
    :disabled="disabled">
        Button
    </button>
</template>

<style scoped></style>