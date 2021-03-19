<template>
  <div>
    <h1>Minha lista de tarefas!</h1>

    <ul>
      <li
        v-for="(task, index) in task"
        :key="`${tasks}-${index}`"
      >
        {{ tasks[0].name}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    tasks: [
      { name: 'fazer a tarefa', isDone: false }
    ]
  })
}
</script>