<template>
    <div class="header">
        <h1>Todo-List</h1>
        <div id="nav">
            <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
        </div>
    </div>
</template>
<script>
export default {
    name: "headerLayout"
}


</script>

<style scoped>
.header{
    background: rgb(78, 57, 57);
    color: white;
    width: 100%;
    text-align: center;

  
}
.header h1{
    font-size: 50px;
    font-weight: 700;
}
.header a{
    padding: 10px;
    margin-top: 20px;
    text-decoration: none;
}
</style>