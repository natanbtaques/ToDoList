<template>
    <div class="new-task">
        <input class="form-element" v-model ="name" @keydown.enter="add" type="text" placeholder="New Task?">
        <button class="form-element" @click="add" >+</button>
    </div>
</template>

<script>
export default{
    data(){
        return{
            name:''
        }
    },
    methods:{
        add(){
            this.$emit('TaskAdded' , {name: this.name})
            this.name= ''
        }
    }
}
</script>

<style>
    .new-task{
        position:relative;
        display: flex;
        text-align: center;
        align-items: center;
        margin: 45px;
        
    }

    .form-element{
        font-size: 2rem;
        outline: none;
        border: 1px solid #FFF;
        padding: 5px 10px 8px ;
        color: #fff;
        
        
        
    }
    input.form-element{
        width: 500px;
        background: #fff2;
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
    }

    button.form-element{
        border-left: none;
        color: #FFF;
        background-color: rgba(103, 103, 255, 0.445);
        border-top-right-radius: 8px;
        border-bottom-right-radius: 8px;
        
    }
</style>