<template>
<div :class="`task ${task.done ? `is-complete` : ''}`">
    <div class="content">{{ task.content }}</div>
    <div class="buttons">
        <button @click="toggleDone">{{ task.done ? 'Undo' : 'Done' }}</button>
        <button @click="removeTask" class="delete">Delete</button>
        <button @click="editTask">{{ task.content ? 'Edit' : 'Save' }}</button>
    </div>
</div>
</template>

<script>
export default {
    props: ['task'],
    methods: {
        toggleDone(task) {
            this.$store.commit('TOGGLE_TASK', this.task);
        },

        removeTask(task) {
            this.$store.commit('REMOVE_TASK', this.task);
        },

        editTask(task) {
            this.$store.commit("EDIT_TASK", this.task);
        }
    }
}
</script>

<style>

</style>