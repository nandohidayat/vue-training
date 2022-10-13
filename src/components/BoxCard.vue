<template>
  <div
    class="w-10 h-10"
    :style="{ backgroundColor: props.boxModel.color }"
    @click="selectBox()"
  ></div>
</template>

<script setup lang="ts">
import type { PropType } from "vue";
import type { BoxModel } from "@/models/BoxModel";

const props = defineProps({
  boxModel: {
    type: Object as PropType<BoxModel>,
    required: true,
  },
});

const emit = defineEmits(["selected"]);

const selectBox = () => {
  emit("selected", props.boxModel);
};
</script>

<style scoped></style>
