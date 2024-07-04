<!-- cách sử dụng không xài scipt setup -->
<!-- <script>
// Khai báo state trong value
import { ref } from 'vue'
export default {
  // `setup` là một hook đặc biệt dành cho Composition API.
  setup() {
    const count = ref(0)
    const increment = () => {
        count.value++
    }
    return {
      count, 
      increment
    }
  }
}
</script> -->
<!-- cách sử dụng  xài scipt setup -->
<!-- <script setup> -->
<!-- // Example 1 - ref()
// import {ref} from 'vue'
// const count = ref(0)
// function increment(){
//     count.value++
// }
// Example 2 - Deep reactivity
import { ref } from "vue";
import { nextTick } from "vue";
const obj = ref({
  nested: { count: 0 },
  arr: ["orange", "banana"],
});
async function mutaDeeply() {
  obj.value.nested.count++;
  obj.value.arr.push("apple");
  await nextTick();
}
</script> -->
<!-- cách sử dụng reactive -->
<script setup>
// import { reactive } from "vue";
// const state = reactive({ count: 0, count1: 1 });
// Mở rộng về Ref
import { ref } from "vue";
import { reactive } from "vue";
const count = ref(0);
const state = reactive({ count });
state.count = 1;
console.log(count.value); // 1
const otherCount = ref(2);
state.count = otherCount;
console.log(count.value); // 1
console.log(state.count); // 2
</script>

<template>
  <!-- Khai báo state trong value -->
  <!-- ref -->
  <!-- <div>{{ count }}</div> -->
  <!-- deep -->
  <!-- <div>{{ obj.nested.count }}</div>
  <div>{{ obj.arr }}</div>
  <button @click="mutaDeeply">Deep</button> -->
  <!-- ref -->
  <!-- <button @click="increment">click 1</button>
  <button @click="count++">Click 2</button> -->
  <!-- reactive -->
  <div>{{ state.count }}</div>
  <div>{{ state.count1 }}</div>
  <button @click="state.count++">Reactive</button>
</template>
