<template>
  <div class="flex">
    <box-card :box-model="box1" @selected="changeColor(box1)"></box-card>
    <box-card :box-model="box2" @selected="changeColor(box2)"></box-card>
    <box-card :box-model="box3" @selected="changeColor(box3)"></box-card>
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";
import BoxCard from "@/components/BoxCard.vue";
import type { BoxModel } from "@/models/BoxModel";

const box1 = reactive({
  id: 1,
  color: "red",
});

const box2 = reactive({
  id: 2,
  color: "blue",
});

const box3 = reactive({
  id: 3,
  color: "green",
});

const random_rgba = () => {
  const o = Math.round,
    r = Math.random,
    s = 255;
  return (
    "rgba(" +
    o(r() * s) +
    "," +
    o(r() * s) +
    "," +
    o(r() * s) +
    "," +
    r().toFixed(1) +
    ")"
  );
};

const changeColor = (boxModel: BoxModel) => {
  boxModel.color = random_rgba();
};
</script>

<style scoped></style>
