<script>
export default {
    data() {
        return {
            count: 0
        }
    }
}
</script>

<template>
    <div class="ciao">
        <h1>Ciao ciao ciao</h1>
    </div>
</template>

<style scoped lang="scss">
@use "../../style/variables" as *;

.ciao {
    background-color: black;
    color: red;
    padding: 20px;
    text-align: center;

    h1 {
        color: $main-color;
    }
}
</style>