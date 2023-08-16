<template>
    <div>
        <h2>Bonjour {{name}} - {{speudo}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'Welcome',
        props: [
            'name',
            'speudo'
        ]
    }
</script>

<style scoped>

</style>