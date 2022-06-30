<template>
  <div>
    <p :class="{ active: isShow }">我是动态class</p>
    <button @click="change">切换</button>
    <p :style="{ fontSize: fz + 'px' }">我是动态style</p>
    <button @click="changeBig">点击我加大字体</button>
  </div>
</template>

<script>
export default {
  name: "Practise3App",

  data() {
    return {
      isShow: "true",
      fz: 20,
    };
  },

  mounted() {},

  methods: {
    change() {
      this.isShow = !this.isShow;
    },
    changeBig() {
      this.fz++;
    },
  },
};
</script>

<style scoped>
.active {
  background-color: red;
}
</style>