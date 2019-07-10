<template>
    <div class="enclosing">
        <form class="form_ele">
            <input type="text" 
            class="input_field"
            v-model="title" 
            name="title" 
            placeholder="Add to do ...">
            <input type="submit" value="Submit" class="btn" v-on:click="addtolist">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name : "Add",
    data()
    {
        return {
            title : ''
        }
    },
    methods : {
        addtolist(e)
        {
            e.preventDefault();
            const newtodo = {
                id : uuid.v4(),
                title : this.title,
                completed : false
            }

            this.$emit('add-tolist',newtodo)
            this.title = ''
        }
    }
}
</script>

<style scoped>
    .input_field
    {
        margin : auto;
        width : 490px;
        height : 40px;
        margin : 10px;
        padding-left : 10px;
        font-size : 20px;
    }
    .btn
    {
        width : 100px;
        height : 40px;
        background-color: black;
        color : white;
        font-size: 20px;
    }
    .form_ele
    {
        margin :auto;
    }

    .enclosing
    {
        border : 1px solid black;
        margin : auto;
        width : 633px;
        margin-top : 10px;

    }
</style>


