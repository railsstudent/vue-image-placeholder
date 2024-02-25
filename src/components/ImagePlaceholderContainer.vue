<script setup lang="ts">
import { ref, computed } from 'vue';
import ImagePlaceholderForm from './ImagePlaceholderForm.vue';

const text = ref('Model');
const width = ref(400);
const height = ref(120);
const color = ref('#fff');
const backgroundColor = ref('#000');

const url = computed(() => {
  const w = width.value;
  const h = height.value;
  const encText = text.value ? encodeURIComponent(text.value) : `${w} x ${h}`;
  const encColor = encodeURIComponent(color.value);
  const encBackground = encodeURIComponent(backgroundColor.value);

  return `https://via.assets.so/img.jpg?w=${w}&h=${h}&tc=${encColor}&bg=${encBackground}&t=${encText}`;
});
</script>

<template>
  <ImagePlaceholderForm
    v-model:text="text"
    v-model:width="width"
    v-model:height="height"
    v-model:color="color"
    v-model:backgroundColor="backgroundColor"
  >
  </ImagePlaceholderForm>
  <p>Url: {{ url }}</p>
  <img :src="url" alt="Image Placeholder" />
</template>

<style scoped>
img {
  margin-top: 1rem;
}
</style>
