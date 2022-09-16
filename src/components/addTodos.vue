<template>
    <form action="" class="addtodo" @submit="Addtodo">
        <input type="text">
        <input type="submit" value="submit">
    </form>
</template>

<script>
export default {
    name: 'addTodos',
    methods:{
        Addtodo(){

        }
    }
}
</script>

<style scoped>
form{
    display: flex;
}
input[type='text']{
    flex: 8;
    height: 50px;
    border: none;
    outline: none;
}
input[type='submit']{
    flex: 3;
    color: blanchedalmond;
    font-size: 30px;
    background-color: red;
    border: none;
    outline: none;
    border-radius: 5px;
}
</style>