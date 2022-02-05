<template>
    <div>
        <h1 v-if="error.statusCode === 404">404 Page not found</h1>
    </div>
</template>

<script>
export default {
    name: "error",
    props: ['error'],
}
</script>

<style scoped>

</style>
