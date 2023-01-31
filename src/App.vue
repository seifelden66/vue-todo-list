<template>
  <div class="container">
    <div class="the-inputs">
      <h2>enter task</h2>
      <textarea v-model="task" />
    </div>
    <div class="buttons">
      <button @click="addTask" :disabled="!task">add task</button>
      <button @click="clearTasks" class="warn">clear list</button>
    </div>
    <ListComp :list="theList" :task="task" :removetask="removeTask" />
  </div>
</template>
<script>
import ListComp from "./components/ListComp.vue";
export default {
  components: {ListComp},
  data() {
    return {
      theList: [],
      task: undefined,
    };
  },
  methods: {
    addTask() {
      this.theList.push(this.task);
      this.task = undefined;
    },
    removeTask(i) {
      this.theList.splice(i, 1);
    },
    clearTasks() {
      this.theList = [];
    },
  },
};
</script>
<style lang="scss" scoped>
.container {
  border-radius: 10px;
  border: 1px solid rgba(0, 0, 0, 0.349);
  padding: 20px;
  width: 50%;
  margin: auto;
  transform: translateY(150px);

  .buttons {
    margin-top: 20px;
    display: flex;
    justify-content: space-evenly;
  }
  .the-inputs {
    margin-top: 20px;
    display: flex;
    justify-content: center;
    gap: 2rem;
    align-items: center;
  }
  textarea {
    border-radius: 10px;
    border: 1px solid rgba(0, 0, 0, 0.349);
    padding: 10px;
    height: 30px;
  }

  // .tasks {
  //   margin-top: 20px;
  //   border: 1px solid rgba(12, 10, 10, 0.24);
  //   border-radius: 10px;
  //   min-height: 200px;
  //   align-items: center;
  //   li {
  //     display: grid;
  //     grid-template-columns: 3fr 0.5fr;
  //     margin-top: 0.5rem;
  //     margin-right: 1rem;
  //     align-items: center;
  //     .tas {
  //       border: 1px solid rgba(12, 10, 10, 0.178);
  //       border-radius: 10px;
  //       padding: 0.5rem;
  //       width: 80%;
  //     }
  //   }
  // }
}
</style>
