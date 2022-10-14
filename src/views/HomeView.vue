<template>
  <div>{{ coords.latitude }} - {{ coords.longitude }}</div>
  <img :src="qrcode" alt="Location" />
</template>

<script setup lang="ts">
import { useTitle, useGeolocation } from "@vueuse/core";
import { useQRCode } from "@vueuse/integrations/useQRCode";

useTitle("Vue is awesome!");
const { coords } = useGeolocation();
const qrcode = useQRCode(
  `https://google.com/maps?q=${coords.latitude},${coords.longitude}`
);
</script>
