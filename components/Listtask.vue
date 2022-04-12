<template>
  <div class="connect-sorting">
    <v-card-title>
      <span class="text-h5">In Progress</span>
      <v-spacer></v-spacer>
      <v-menu bottom left>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, i) in items" :key="i">
            <v-list-item-title>
              {{ item.title }}
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-card-title>
    <div class="pt-4 pb-4">
      <taskcard></taskcard>
    </div>
    <div class="pb-4 mt-4">
      <addtask></addtask>
    </div>
  </div>
</template>

<script>
import Addtask from "../components/Addtask.vue";

export default {
  components: {
    Addtask,
  },
  data: () => ({
    items: [{ title: "แก้ไข" }, { title: "ลบ" }],
  }),
};
</script>

<style scoped>
.connect-sorting {
  padding: 15px;
  border-radius: 10px;
  border: 1px solid #e0e6ed;
  background: #e2e6ea;
}
</style>
