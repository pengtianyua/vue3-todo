<template>
  <div class="wrapper">
    VUE3+TypeScript
    <todo-input ref="todoInp" />
    <todo-list :todo-list="todoList"/>
  </div>
</template>

<script lang="ts">
import {computed, defineComponent, onMounted, ref} from "vue";
import TodoInput from './components/TodoInput/index.vue'
import TodoList from './components/TodoList/index.vue'
import {IUseTodo, useTodo} from '../hooks'
import {Store, useStore} from "vuex";

export default defineComponent({
  name: 'App',
  components: {
    TodoInput,
    TodoList
  },
  setup() {
    const todoInp = ref(null)
    const {setTodoList}: IUseTodo = useTodo()
    const store: Store<any> = useStore()
    onMounted(() => {
      setTodoList()
      console.log(todoInp.value)
    })
    return {
      todoInp,
      todoList: computed(() => store.state.list)
    }
  }
})
</script>
