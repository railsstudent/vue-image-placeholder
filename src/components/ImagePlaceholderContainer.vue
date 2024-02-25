<script setup lang="ts">
import { ref, computed, watchEffect } from 'vue';
import ImagePlaceholderForm from './ImagePlaceholderForm.vue';

const text = ref('Reactivity');
const width = ref(250);
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

watchEffect(() => {
  console.log('New text', text.value);
  console.log('New width', width.value);
  console.log('New height', height.value);
  console.log('New color', color.value);
  console.log('New background color', backgroundColor.value);
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
p {
  padding-top: 1rem;
  padding-bottom: 1rem;
}

img {
  margin-top: 0.5rem;
}
</style>
