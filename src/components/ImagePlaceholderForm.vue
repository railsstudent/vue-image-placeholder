<script setup lang="ts">
const text = defineModel('text', { type: String, default: 'Input' });
const width = defineModel('width', { type: Number, required: true });
const height = defineModel('height', { type: Number, default: 120 });
const textColor = defineModel('color', { type: String, default: '#fff' });
const bgColor = defineModel('backgroundColor', { type: String, default: '#000' });
</script>

<template>
  <h3>Redo https://dev.me/products/image-placeholder with defineModel</h3>
  <div class="container">
    <div class="field">
      <label for="text">
        <span>Text: </span>
        <input name="text" id="name" v-model="text" />
      </label>
    </div>
    <div class="field">
      <label for="width">
        <span>Width: </span>
        <input name="width" id="width" type="number" v-model="width" />
      </label>
    </div>
    <div class="field">
      <label for="height">
        <span>Height: </span>
        <input name="height" id="height" type="number" v-model="height" />
      </label>
    </div>
    <div class="field">
      <label for="color">
        <span>Color: </span>
        <input name="color" id="color" v-model="textColor" />
      </label>
    </div>
    <div class="field">
      <label for="backgroundColor">
        <span>Background Color: </span>
        <input name="backgroundColor" id="backgroundColor" v-model="bgColor" />
      </label>
    </div>
  </div>
</template>

<style scoped>
h3 {
  margin-bottom: 1rem;
}

div.container {
  width: 50%;
  padding: 0.5rem;
  border: 1px solid black;
  border-radius: 12px;
}

div.field {
  padding: 0.25rem;
}

input {
  padding: 0.5rem;
  border: 1px solid #4aa;
  border-radius: 8px;
}
</style>
