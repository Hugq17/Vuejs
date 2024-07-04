<script setup>
const message = "hellow world";
const rawHtml = "<h1>How are you today</h1>"; // raw HTML
const buttonId = "button-id";
const buttonClass = "button-class";
const rawHtml2 = "<h1>Hello</h1>";
const buttonId1 = "buttonID1";
const buttonClass1 = "buttonCLASS1";
const isButtonDisabled = true;
//  vô hiệu hóa button
const objectOfAttrs = {
  id: "container",
  class: "wrapper",
  style: {
    color: "pink",
  },
};
const number = 0
const listString = 'a, b, c, d, e, f, g'
const convertToId = (data) => data.split(',').reverse().join('-') 
</script>

<template>
  <h1>Syntax</h1>
  <p>Message: {{ message }}</p>
  <!-- sử dụng 2 cặp {{}} để truyền biến vào-->
  <span v-html="rawHtml"></span>
  <button :id="buttonId" :class="buttonClass">Click me</button>
  <!-- sử dụng : Ràng buộc thuộc tính-->
  <span v-html="rawHtml2"></span>
  <button :id="buttonId1" :class="buttonClass1" :disabled="isButtonDisabled">
    {{ isButtonDisabled ? 'Disabled' : 'click me' }}
  </button>
  <!-- vô hiệu hóa button -->
  <button v-bind="objectOfAttrs">Click here !!!</button>
  <button :id="listString.split(',').join('-')">Number: {{number}}</button>
  <button :id="convertToId(listString)">Click me</button>
</template>
