<template>
    <div class="todo__add-field">
    <input @keyup.enter="addTask" v-model="text" type="text" placeholder="Введите текст задачи...">
    <button @click="addTask" class="todo__add-field-button">
        <svg height="20px" viewBox="0 0 448 448" width="20px"><path d="m408 184h-136c-4.417969 0-8-3.582031-8-8v-136c0-22.089844-17.910156-40-40-40s-40 17.910156-40 40v136c0 4.417969-3.582031 8-8 8h-136c-22.089844 0-40 17.910156-40 40s17.910156 40 40 40h136c4.417969 0 8 3.582031 8 8v136c0 22.089844 17.910156 40 40 40s40-17.910156 40-40v-136c0-4.417969 3.582031-8 8-8h136c22.089844 0 40-17.910156 40-40s-17.910156-40-40-40zm0 0"></path></svg>
    </button>
</div>

</template>

<script>
export default {
    data:()=>({
        text:""
    }),
    methods:{
        addTask(){
            if(this.text){
                this.$emit('onaddtask',this.text.trim())
                this.text = ""
            }
        },
        
    }
}
</script>