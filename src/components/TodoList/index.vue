<template>
  <div>
    Todo-list
    <todo-item
      v-for="item of todoList"
      :key="item.id"
      :item="item"
      @removeTodo="removeTodo"
      @setStatus="setStatus"
      @setDoing="setDoing"
    />
  </div>
</template>

<script lang="ts">
import {defineComponent, PropType} from "vue";
import TodoItem from './item.vue'
import {ITodo} from "@/typings";
import {IUseTodo, useTodo} from "../../../hooks";

export default defineComponent({
  name: "TodoList",
  components: {
    TodoItem
  },
  props: {
    todoList: Array as PropType<ITodo[]>
  },
  setup() {
    const {removeTodo, setStatus, setDoing}: IUseTodo = useTodo()
    return {
      removeTodo,
      setStatus,
      setDoing
    }
  }
})
</script>

<style scoped>

</style>