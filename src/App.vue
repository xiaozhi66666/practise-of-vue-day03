<template>
  <div id="app">
    <ul>
      <li v-for="item in myArr" :key="item">{{ item }}</li>
    </ul>
    <button @click="btnFn">走一走</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myArr: ["帅哥", "美女", "程序猿"],
    };
  },
  methods: {
    btnFn() {
      // 将数组第一个添加到最后一位
      this.myArr.push(this.myArr[0]);
      // 删除第一个
      this.myArr.shift();
    },
  },
};
</script>