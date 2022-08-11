<template>
  <div class="d-flex justify-content-center align-items-center">
    <label class="gorevLabel">Eklenecek Görev:</label>
    &nbsp; &nbsp;
    <label for="todoText "></label>
    <input
      class="ilkHarfBuyuk"
      v-model="todoText"
      @keydown.enter="addNewTodo(todoText)"
      type="text"
      id="todoText"
      placeholder="Bir şeyler yazınız..."
    />
  </div>
</template>

<script>
export default {
  props: {
    addNewTodo: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      todoText: null,
    };
  },
  methods: {},
};
</script>
