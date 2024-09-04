<template>
  <div><h1>My Todo</h1></div>
  <h3>{{ completeAll }}</h3>
  <ItemList :Items="DataItemList" @onChangeItem="CompletedItems"> </ItemList>
</template>
<script setup lang="ts">
import { computed, reactive } from "vue";
import ItemList from "./components/Items/Items.componet.vue";
import type { ItemInterface } from "./models";
const DataItemList: ItemInterface[] = reactive([
  {
    id: 1,
    name: "Task1",
    completed: false,
  },
  {
    id: 2,
    name: "Task2",
    completed: true,
  },
  {
    id: 3,
    name: "Task3",
    completed: false,
  },
  {
    id: 3,
    name: "Task4",
    completed: false,
  },
  {
    id: 3,
    name: "Task5",
    completed: false,
  },
  {
    id: 3,
    name: "Task6",
    completed: false,
  },
  {
    id: 3,
    name: "Task7",
    completed: false,
  },
]);

const CompletedItems = (id: any) => {};

const completeAll = computed(() => {
  let all = DataItemList.length;
  let countCompleted = 0;

  DataItemList.forEach((e) => {
    if (e.completed) {
      countCompleted++;
    }
  });
  return countCompleted == all ? "[All todo is completed]" : "[No]";
});
</script>
