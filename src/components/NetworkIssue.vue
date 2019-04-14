<template>
    <div>
        <h1> UH-OH!</h1>
        <h3>It looks like you're experiencing some network issues, please click your back button </h3>
        <router-link :to="{ name: 'event-list' }"
        >Or go back to the home page</router-link
        >
    </div>
</template>

<script>
    export default {
        name: "NetworkIssue"
    }
</script>

<style scoped>

</style>