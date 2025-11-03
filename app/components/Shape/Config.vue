<script setup lang="ts">
import { ref } from 'vue';

interface ShapeData {
  shape: string;
  sideLength?: number;
  radius?: number;
}

const formData = ref<ShapeData>({
      shape: '',
});

function handleFormSubmission() {
  console.log(`Shape: ${formData.value.shape}`);
  if (formData.value.shape === 'triangle') {
    console.log(`Side length: ${formData.value.sideLength}`);
  } else if (formData.value.shape === 'circle') {
    console.log(`Radius: ${formData.value.radius}`);
    }
}
</script>

<template>
  <div>
    <h1>Shape</h1>
    <form @submit.prevent="handleFormSubmission">
      <label for="shape">Choose a shape:</label>
      <br />
      <input type="radio" id="triangle" v-model="formData.shape" value="triangle" />
      <label for="triangle">Triangle</label>
      <br />
      <input type="radio" id="circle" v-model="formData.shape" value="circle" />
      <label for="circle">Circle</label>
      <br />
      <div v-if="formData.shape === 'triangle'">
        <label for="length">Side length:</label>
        <br />
        <input type="number" id="length" v-model="formData.sideLength" />
      </div>
      <div v-else-if="formData.shape === 'circle'">
        <label for="radius">Radius:</label>
        <br />
        <input type="number" id="radius" v-model="formData.radius" />
      </div>
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

