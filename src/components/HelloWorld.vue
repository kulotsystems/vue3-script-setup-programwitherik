<template>
    <div>
        <h3>Hello from component.</h3>
        <h5>Received name: {{ props.name }}</h5>

        <button @click="getAlert">Press Me</button>
    </div>
</template>

<script setup>
    const props = defineProps({
        name: String
    });

    const emits = defineEmits(['pressed']);

    const getAlert = () => {
        emits('pressed', 'Whatever');
    };
</script>


<style scoped>
    .green {
        background-color: green;
        color: white;
        padding: 15px;
    }
</style>
