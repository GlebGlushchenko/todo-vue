
<template>
  <div class="todo">
        <div class="todo__header">
    <h4>Список задач</h4>
</div>
    <TaskField @onaddtask="onAddTask" />
<div class="todo__list">
    <ListItem v-for="(task,index) in tasks" 
     :key="index" 
    :text="task.text" 
    :index="index"
    :completed="task.completed"
    @ontogglecomplited="onToggleComplited"
    @onremovetask='onRemoveTask'
    />
    
</div>
    </div>
</template>

<script>
import ListItem from './components/ListItem.vue'
import TaskField from './components/TaskField'

export default {
  name: 'App',
  data:()=>({
    tasks:[{ 
      text:"Изучить Vue JS",
      completed:true
    },{
      text:"Разработать Todo на Vue JS",
      completed:false
    }]
  }),
  methods:{
    onToggleComplited(index){
      this.tasks[index].completed =! this.tasks[index].completed
    },
    onAddTask(text){
      this.tasks.push({
        text,
        completed:false
      })
    },

    onRemoveTask(index){
      this.tasks.splice(index,1)
    }

  },
 
  components: {
    ListItem,
    TaskField
  },
}
</script>

<style>
@import './assets/base.css';
</style>
