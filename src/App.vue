<template>
  <div id="app">
    <ul>
      <li v-for="(item, ind) in arr" :key="ind">
        <span>{{ item }}</span>
        <button @click="delFn(index)">删除</button>
      </li>
    </ul>
    <button @click="addFn">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 5, 3],
    };
  },
  methods: {
    // 删除
    delFn(ind) {
      this.arr.splice(ind, 1);
    },
    // 添加
    addFn() {
      // 定义一个获取指定随机整数的方法;
      function getRandomIntInclusive(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min; //含最大值，含最小值
      }
      const num = getRandomIntInclusive(1, 10);
      // 数组追加随机数
      this.arr.push(num);
    },
  },
};
</script>