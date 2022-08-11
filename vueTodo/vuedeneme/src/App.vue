<template>
  <div class="container">
    <h3 class="text-center d-flex justify-content-center purple">ToDo App</h3>
    <hr class="my-2" />
    <AddSection :addNewTodo="addNewTodo" @add-todo="addNewTodo" />
    <ListSection />
  </div>
</template>

<script>
import AddSection from "@/components/AddSection";
import ListSection from "@/components/ListSection";
export default {
  components: {
    AddSection,
    ListSection,
  },

  data() {
    return {
      provideData: {
        todoList: [
          { id: 1, text: "Todo 1" },
          { id: 2, text: "Todo 2" },
          { id: 3, text: "Todo 3" },
          { id: 4, text: "Todo 4" },
        ],
      },
    };
  },
  provide() {
    return {
      provideData: this.provideData,
      deleteItem: this.deleteItem,
    };
  },
  methods: {
    deleteItem(todoItem) {
      this.provideData.todoList = this.provideData.todoList.filter(
        (t) => t != todoItem
      );
    },
    addNewTodo(todo) {
      this.provideData.todoList.push({
        id: new Date().getTime(),
        text: todo,
      });
    },
  },
};
</script>
