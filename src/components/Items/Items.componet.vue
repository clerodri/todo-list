<template>
  <div>Tasks :</div>

  <ul v-for="data in Items" :key="data.id">
    <li>
      {{ data.name }} -
      <input
        type="checkbox"
        v-model="data.completed"
        @click="completedItems(data.id)"
      />
    </li>
  </ul>
</template>
<script setup lang="ts">
import type { ItemInterface } from "../../models";

//define props data
defineProps<{ Items: ItemInterface[] }>();

// define function callback to parent for changes
const emit = defineEmits<{ (e: "onChangeItem", id: number): any }>();

//Functions completed items
const completedItems = (id: any) => {
  // change the state of co mpleted
  emit("onChangeItem", id);
};
</script>

<style lang=""></style>
