<script>
export default {
    data() {
        return {
            name: 'AppMain',
        }
    }
}
</script>

<template>
    <button @click="count++">You clicked me {{ count }} times.</button>
</template>

<style scoped></style>