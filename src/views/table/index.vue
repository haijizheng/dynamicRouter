<template>
  <el-row>
    姓名：{{info.name}}
    <el-input v-model="info.name" placeholder="请输入姓名"></el-input>
    年龄：{{info.age}}
    <el-input v-model="info.age" placeholder="请输入年龄"></el-input>
    性别：{{info.sex}}
    <el-select v-model="info.sex" placeholder="请选择">
      <el-option v-for="item in options" :key="item" :value="item"></el-option>
      <!-- 这里的key官方推荐在v-for时使用，不然会警告，但不影响使用 -->
    </el-select>
    <el-button>创建</el-button>
    <template>
      <el-table :data="tabledata" align="left">
        <el-table-column prop="name" label="姓名"></el-table-column>
        <el-table-column prop="age" label="年龄"></el-table-column>
        <el-table-column prop="sex" label="性别"></el-table-column>
        <el-table-column label="操作">
          <template slot-scope="a">
            <el-button size="mini" type="danger" @click="del(a.$index)">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
    </template>
  </el-row>
</template>
<script>
export default {
  data() {
    return {
      info: {
        name: "",
        age: null,
        sex: ""
      },
      options: ["女", "男", "保密"],
      tabledata: [
        //这里的内容是方便我们看到table的变化，可见页面上的table有了如下的内容
        { name: "Leo", age: 12, sex: "man" },
        { name: "Lei", age: 22, sex: "women" },
        { name: "Lii", age: 65, sex: "men" }
      ]
    };
  }
};
</script>
<style>
</style>