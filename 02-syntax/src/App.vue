<script setup>
// html thô
const rawHtml = '<span style="color: pink">Hi hi hi</span>'
// Ràng buộc thuộc tính
const idDiv = "idDIV"
// Bí danh cùng tên: cùng là tên id
const id = "idHi"
// Thuộc tính boolean
const DisButton = true
// Ràng buộc động nhiều thuộc tính
const objectDiv = {
  id: "idButton",
  class: "classButton"
}
// Sử dụng biểu thức JS
const name = "Quang Hung"
// Directives
// Đối số
const seen = false
const url = "https://vuejs-course.vercel.app/guide/essentials/template-syntax.html"
const doSomething = () => {
  console.log("Hi ae")
}
// Đối số động
const href1 = "href"
const eventname = "click"
</script>

<template>
  <!-- html thô -->
  <div v-html='rawHtml'></div>
  <!-- Ràng buộc thuộc tính -->
  <div :id="idDiv">Xin chào Vuejs</div>
  <!-- Bí danh cùng tên -->
  <div :id>Hi ae</div>
  <!-- Thuộc tính boolean -->
  <button :disabled="DisButton">Click</button>
  <!-- Ràng buộc động nhiều thuộc tính -->
  <div v-bind="objectDiv">Bạn bao nhiêu tuổi</div>
  <!-- Sử dụng biểu thức JS -->
  <div>{{ name }}</div>
  <!-- Directives -->
  <p v-if="seen">Bây giờ bạn thấy tôi</p>
  <!-- Đối số: href là đối số, mọi thứ trước đối số đều có thể viết tắt là : -->
  <!-- Examlple 1 -->
  <a v-bind:href="url">Doi So</a>
  <a :href="url">Doi so 2</a>
  <!-- Example 2 -->
  <!-- v-on viết tắt @ -->
  <a v-on:click="doSomething">Link</a>
  <a @click="doSomething">Link2</a>
  <!-- Đối số động -->
  <a v-bind:[href1]="url">Link3</a>
  <a :[href1]="url">Link4</a>
  <a @[eventname]="doSomething">Click</a>
</template>