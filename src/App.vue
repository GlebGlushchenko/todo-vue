
<template>
  <div class="todo">
        <div class="todo__header">
    <h4>Список задач</h4>
</div>
    <TaskField />
<div class="todo__list">
    <ListItem v-for="(task,index) in tasks" 
     :key="index" 
    :text="task.text" 
    :index="index"
    :completed="task.completed"
    @ontogglecomplited="onToggleComplited"/>
    
</div>
    </div>
</template>

<script>
import ListItem from './components/ListItem.vue'
import TaskField from './components/TaskField'

export default {
  name: 'App',
  methods:{
    onToggleComplited(index){
      this.tasks[index].completed =! this.tasks[index].completed
    }
  },
  data:()=>({
    tasks:[{ 
      text:"Изучить Vue JS",
      completed:true
    },{
      text:"Разработать Todo на Vue JS",
      completed:false
    }]
  }),
  components: {
    ListItem,
    TaskField
  }
}
</script>

<style>
@import './assets/base.css';
</style>
