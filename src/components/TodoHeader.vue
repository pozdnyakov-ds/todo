<template>
    <div style="width: 100%; height: 75px; background-color: #eee; padding: 10px; text-align: left; display: flex">
        <img alt="ToDo logo" src="../assets/logo.png" style="width: 50px; height: auto; display: inline-block; margin: 0 20px 0 5px;">
        <div class="header">{{ title }}</div> 
        <div class="login">Логин</div>
    </div>
</template>

<script>
    export default {
          props: ['title'],
        
    }
</script>

<style scoped>
.header {
    width: 80%; 
    margin-left: 10px; 
    margin: auto;
    padding: 5px; 
    display: inline-block;
    background-color: transparent;
    font-weight: bold;
}
.login {
    width: 10%; 
    margin: auto;
    padding: 10px;
    display: inline-block;
    background-color: #fff;
    border-radius: 5px;
}
</style>