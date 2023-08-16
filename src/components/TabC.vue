<template>
    <div>
        <h2>Component TabC</h2>
        <h2>{{info}}</h2>
        <input type="text" v-model="info">
        <br>
    </div>
</template>

<script>
    export default {
        name: 'TabC',
        data(){
            return{
                info: '',
            }
        }
    }
</script>

<style scoped>

</style>