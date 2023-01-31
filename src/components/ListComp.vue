<template>
  <div class="tasks">
    <ul>
      <li v-for="(task, i) in list" :key="i">
        <div class="tas">{{ task }}</div>
        <button @click="removeTask(i)" class="warn">x</button>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  props: ["list", "task"],
  methods: {
    removeTask(i) {
      this.list.splice(i, 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.tasks {
  margin-top: 20px;
  border: 1px solid rgba(12, 10, 10, 0.24);
  border-radius: 10px;
  min-height: 200px;
  align-items: center;
  li {
    display: grid;
    grid-template-columns: 3fr 0.5fr;
    margin-top: 0.5rem;
    margin-right: 1rem;
    align-items: center;
    .tas {
      border: 1px solid rgba(12, 10, 10, 0.178);
      border-radius: 10px;
      padding: 0.5rem;
      width: 80%;
    }
  }
}
</style>
