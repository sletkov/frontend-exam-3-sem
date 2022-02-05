<template>
    <div class="default">
        <Header class="row-cols-12"/>
        <div class="row">
            <Sidebar class="col-3"/>
            <Nuxt class="col-8"/>
        </div>
<!--        <Footer class="row-cols-12" />-->
    </div>
</template>

<script>
export default {
    name: "default"
}
</script>

<style scoped>
    html, body {
        min-height: 100%;
    }
</style>
