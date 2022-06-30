<template>
  <div>
    <ul>
      <li
        v-for="(item, index) in navs"
        :key="index"
        :class="{ active: index === activeIndex }"
        @click="activeFn(index)"
      >
        <!-- 利用动态类名设置，判断当前点击保存下来的索引是否与遍历出来的li是否相等，如果相等就让这个类显示，否则就不显示 -->
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Practise3App",

  data() {
    return {
      // 数据
      navs: ["大学起点", "高中起点", "初中起点", "小学起点"],
      activeIndex: 0, //设置一个变量来保存当前点击到的index
    };
  },

  mounted() {},

  methods: {
    // 添加方法点击谁就将谁的index保存下来给一个变量
    activeFn(val) {
      // val代表当前索引
      // console.log(val);
      this.activeIndex = val;
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  border-radius: 10px;
  width: 400px;
  overflow: hidden;
  padding: 0;
}
ul li {
  float: left;
  width: 100px;
  height: 40px;
  background-color: #ccc;
  color: #fff;
  text-align: center;
  line-height: 40px;
  cursor: pointer;
}
li.active {
  background-color: blue;
}
</style>