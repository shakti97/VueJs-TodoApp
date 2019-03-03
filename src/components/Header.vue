<template>
    <div class="header">
        <div><img alt="Vue logo" width='100px' height='100px' src="../assets/logo.png">
        <span class='heading'>TODO APP</span></div>
    </div>
</template>

<script>
export default {
    name : 'Header',
    props : {
        header_name : String
    }
}
</script>

<style scoped>
.header{
    padding: 5%;
    background-color: rgb(33, 33, 63);
}
.heading{
    color: rgb(165, 161, 161);
    font-size : 60px;
    font-weight: 800;
    vertical-align: middle;
}
</style>