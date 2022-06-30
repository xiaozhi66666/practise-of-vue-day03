<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addFn">添加/修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="edit(index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      age: "",
      sex: "",
      arr: [],
      obj: {},
      isShow: false,
      index1: 0,
    };
  },
  methods: {
    addFn() {
      if (this.name.trim().length === 0 || this.age.trim().length === 0) {
        alert("请输入有效值");
        return;
      }
      if (this.isShow) {
        // console.log(this.index1);
        // console.log();
        this.arr[this.index1].name = this.name;
        this.arr[this.index1].age = this.age;
        this.arr[this.index1].sex = this.sex;
      } else {
        this.obj = { name: this.name, age: this.age, sex: this.sex };
        this.arr.push(this.obj);
        (this.name = ""), (this.age = "");
      }
    },
    delFn(ind) {
      this.arr.splice(ind, 1);
    },
    edit(ind) {
      this.isShow = true;
      this.index1 = ind;
      this.name = this.arr[ind].name;
      this.age = this.arr[ind].age;
    },
  },
};
</script>
