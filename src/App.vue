<template>
  <div id="app">
    <!-- 语法1:
      v-for="(值变量名, 索引变量名) in 目标结构"
      口诀: 想要谁循环就放到谁身上
     -->
    <p v-for="(item, index) in arr" :key="index">
      第{{ index + 1 }}个学生的名字是：{{ item }}
    </p>

    <p>学生详细信息</p>
    <ul>
      <li v-for="item in stuArr" :key="item.id">
        {{ item.name }} -- {{ item.sex }}-- {{ item.hobby }}
      </li>
    </ul>

    <!-- v-for遍历对象(了解) -->
    <p>老师信息</p>
    <ul>
      <li v-for="item in tObj" :key="item">
        <span>{{ item }}</span>
        <span></span>
        <span></span>
      </li>
    </ul>

    <div></div>

    <!-- v-for遍历整数(了解) - 从1开始 -->
    <p>序号</p>
    <div v-for="item in count" :key="item">{{ item }}</div>
  </div>
</template>

<script>
export default {
  name: "Practise3App",

  data() {
    return {
      arr: ["小明", "小欢欢", "大黄"],
      stuArr: [
        {
          id: 1001,
          name: "孙悟空",
          sex: "男",
          hobby: "吃桃子",
        },
        {
          id: 1002,
          name: "猪八戒",
          sex: "男",
          hobby: "背媳妇",
        },
      ],
      tObj: {
        name: "小黑",
        age: 18,
        class: "1期",
      },
      count: 10,
    };
  },

  mounted() {},

  methods: {},
};
</script>

<style lang="scss" scoped>
</style>