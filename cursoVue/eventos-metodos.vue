<template>
  <div>
    <h1>Minha lista de tarefas</h1>
    <button @click="handleShowHideList">Ver a Lista</button>
    <br />
    <input
      type="text"
      @keyup.enter="addTask"
      v-focus
      v-model="currentTask"
      @keyup="addTask"
    />
    <ul v-if="showList">
      <li
        v-for="(task, index) in tasks"
        @dblclick="complete(task)"
        :key="`${task}-${index}`"
        class="task-item"
        :class="{ 'line-through': task.isDone }"
      >
        {{ task.name }}
        <button @click="remove(task)">&times;</button>
      </li>
    </ul>
    <p v-else>Lista de tarefas escondidas</p>
  </div>
</template>

<script>
const focus = {
  inserted: (el) => {
    el.focus();
  },
};
export default {
  directives: {
    focus,
  },
  data: () => ({
    currentTask: "",
    showList: false,
    tasks: [{ name: "Fazendo o curso", isDone: false }],
  }),
  methods: {
    handleShowHideList() {
      //evento para aparecer e sumir lista
      this.showList = !this.showList;
    },
    addTask() {
      //um array, colocar mais um item no array e depois zerar o input ( currentTask)
      this.tasks.push({
        name: this.currentTask,
        isDone: false,
      });
      //depois de adicionado o item, limpa o input
      this.currentTask = "";
    },
    complete(task) {
      //ter a mesma lista mas com isDone false ou true
      this.tasks = this.tasks.map((t) => {
        if (t.name === task.name) {
          return { ...t, isDone: !t.isDone };
        }
        return { ...t };
      });
    },
    remove(task) {
      //evento para remover item lista
      this.tasks = this.tasks.filter((t) => t.name !== task.name);
    },
  },
};
</script>

<style scoped>
.line-through {
  text-decoration: line-through;
}
.task-item {
  cursor: pointer;
}
</style>