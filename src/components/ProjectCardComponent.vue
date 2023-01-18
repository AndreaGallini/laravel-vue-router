<template>
    <div>
        <h1>{{ obj.nome_progetto }}</h1>
    </div>
</template>

<script>
    export default {
    name: 'ProjectCardComponent',
        props:["obj"]
    }
</script>

<style lang="scss" scoped>

</style>