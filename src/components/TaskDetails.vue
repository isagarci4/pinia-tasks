<script setup lang="ts">
    const props = defineProps({
        task: {
            type: Object,
            required: true,
        }
    })
</script>

<template>
    <div class="task">
        <h3>{{ props.task.title }}</h3>
        <div class="icons">
            <i class="material-icons">delete</i>
            <i class="material-icons">favorite</i>
        </div>
    </div>
</template>

