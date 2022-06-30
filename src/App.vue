<template>
  <div>
    <ul>
      <li v-for="(val, index) in arr" :key="index">
        {{ val }}
      </li>
    </ul>
    <button @click="revBtn">数组翻转</button>
    <button @click="sliceBtn">截取前3个</button>
    <button @click="updateBtn">更新第一个元素值</button>
  </div>
</template>

<script>
export default {
  name: "Practise3App",

  data() {
    return { arr: [5, 3, 9, 2, 1] };
  },

  mounted() {},

  methods: {
    revBtn() {
      this.arr.reverse();
    },
    sliceBtn() {
      this.arr = this.arr.splice(0, 3);
    },
    updateBtn() {
      // 更新第一个元素值，2种方法
      // 1：直接赋值覆盖
      // this.arr = [100, 3, 9, 2, 1];
      // 2:利用vue的$set()方法修改制定位置的值
      this.$set(this.arr, 0, 1000);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>