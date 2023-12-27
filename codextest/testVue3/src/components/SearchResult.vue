<template>
  <div class="search-result">
    <!-- 在这里添加你的模板代码 -->
    <h5>h5标签</h5>
  </div>
  <a href="https://vitejs.dev" target="_blank">
    <img src="/vite.svg" class="logo" alt="Vite logo" />
  </a>
  <button @click="increment">
    {{ count }}
  </button>
 <!-- 姓:<input v-model="Person.X" /><br />
  名:<input v-model="Person.M" /><br />
  单向响应:<input v-model="Person.XM" />-->
</template>

<style scoped>
/* 在这里添加你的样式 */
.search-result {
  color: hwb(71 0% 0%);
}
</style>
<script setup>
import { ref,onMounted } from "vue";
export default {
  name: "SearchResult",
  setup() {
    let box = ref(null); //本质是reactive({value:null})

    // 需要在生命周期获取
    onMounted(()=>{
      // 当界面挂载出来后就会自动执行
      console.log(box.value);
    })
    //接受的是null,原因是setup执行时机比mounted早,dom还没形成
    console.log(box.value);
    return { box };
  },
};
</script>
<!-- <script setup lang="ts">
//setup lang="ts"
// export default {
//   name: "SearchResult",
//   // 在这里添加你的组件选项，例如 data, methods 等
// };

import { ref, computed, reactive, watch, onBeforeMount, onMounted } from "vue";

// const obj = {
//   count: ref(1),
// };
const count = ref(0);

function increment() {
  count.value++;
}
const Person = reactive({
  name: "张三",
  M: "三",
  age: 18,
  job: { salary: 20 },
});
Person.AXM = computed({
  get() {
    return Person.X + "-" + Person.M;
  },
  set(value) {
    const arr = value.split("-");
    Person.X = arr[0];
    Person.M = arr[1];
  },
});
watch(Person, (newVal, oldVal) => {
  console.log("用户信息发生了变化", newVal, oldVal);
});
watch(
  () => Person.age,
  (newVal, oldVal) => {
    console.log("用户年龄发生了变化", newVal, oldVal);
  }
);
watch([() => Person.name, () => Person.age], (newValue, oldValue) => {
  console.log("person.name或者person.age的值变化了", newValue, oldValue);
});
onBeforeMount(() => {
  console.log("---挂载之前---");
});
onMounted(() => {
  console.log("---挂载---");
});
// export default {
//   // data() {
//   //   return {};
//   // },
//   props: {
//     text: {
//       type: String,
//     },
//   },
//   beforeCreate() {
//     console.log("子组件————beforeCreate...");
//   },
//   // created() {
//   //   console.log("子组件————create...");
//   // },
//   // beforeMount() {
//   //   console.log("子组件————beforeMount...");
//   // },
//   // mounted() {
//   //   console.log("子组件————mounted...");
//   // },

//   // beforeUpdate() {
//   //   console.log("子组件————beforeUpdate...");
//   // },

//   // updated() {
//   //   console.log("子组件————updated...");
//   // },

//   // beforeDestroy() {
//   //   console.log("子组件————beforeDestroy...");
//   // },

//   // destroyed() {
//   //   console.log("子组件————destroyed...");
//   // },
// };
// created() {
//  console.log('count is: ' + this.count)
// }
</script> -->

