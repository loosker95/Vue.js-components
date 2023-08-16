<template>
<hr>
    <div>
        <h2>This is the article page</h2>
        <h2>{{title}} {{like}} </h2>
        <h4>Published - {{isPublished ? 'Yes' : 'No'}}</h4>
    </div>
</template>

<script>
    export default {
        name: 'Article',
        props : {
            'title': {
                type: String,
                required: true,
                default: 'This is the default title',
            },
            'like': Number,
            'isPublished': Boolean,
        }
    }
</script>

<style scoped>

</style>