<script setup>
const message = "hellow world";
const rawHtml = "<h1>How are you today</h1>"; // raw HTML
const buttonId = "button-id";
const buttonClass = "button-class";
</script>

<template>
  <h1>Syntax</h1>
  <p>Message: {{ message }}</p>
  <!-- sử dụng 2 cặp {{}} để truyền biến vào-->
  <span v-html="rawHtml"></span>
  <button :id="buttonId" :class="buttonClass">Click me</button>
  <!-- sử dụng : Ràng buộc thuộc tính-->
</template>
