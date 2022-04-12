<template>
  <div class="pl-8 pt-8">
    <addlist></addlist>
    <div class="row todo-section mt-10 pt-6">
      <div class="col-lg-12">
        <div class="task-list-section">
          <div class="task-list-container">
            <listtask> </listtask>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Addlist from "../components/Addlist.vue";
import Listtask from "../components/Listtask.vue";
import Taskcard from "../components/Taskcard.vue";
export default {
  components: {
    Addlist,
    Listtask,
    Taskcard,
  },
};
</script>

<style scoped>
.todo-section {
  border-top: 1px solid #ddd;
}
.task-list-section {
  display: flex;
  overflow-x: auto;
  flex-wrap: nowrap;
  padding-bottom: 15px;
}
.task-list-container {
  min-width: 400px;
  padding: 0 15px;
  width: 400px;
}
</style>