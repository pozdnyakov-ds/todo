<template>
    <div style="width: 100%; height: 50px; background-color: #eee; padding: 10px; text-align: left; display: flex">
        <img alt="ToDo logo" src="../assets/logo.png" style="width: 50px; display: inline-block; margin: 0 20px 0 5px;">
        <div class="header">{{ title }}</div> 
        <div class="login">Логин</div>
    </div>
</template>

<script>
    export default {
          props: ['title'],
        
    }
</script>

<style>
.header {
    width: 80%; 
    margin-left: 10px; 
    margin: auto;
    padding: 5px; 
    display: inline-block;
    background-color: aquamarine;
}
.login {
    width: 20%; 
    margin-left: 10px; 
    margin: auto; 
    padding: 5px;
    display: inline-block;
    background-color: #ccc;
}
</style>