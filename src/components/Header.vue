<template>
    <header>
        <h1>{{ title }}</h1>
        <!-- <Button text="view user skills" color="green" /> -->
    </header>
</template>


<script>
import Button from './Button'
export default {
   name: "Header",
    props: {
        title: String,
        showAddTask: Boolean,
    },
    components: {
        Button,
    },
}
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 20px;
}
</style>