<template>
    <div>
        <h2>Component C</h2>
        <p>The name from component C is: {{name}}</p>
    </div>
</template>

<script>
    export default {
        name: 'ComponentC',
        inject:['name']
    }
</script>

<style scoped>

</style>