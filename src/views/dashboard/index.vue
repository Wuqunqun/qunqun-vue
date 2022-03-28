<template>
  <div class="dashboard-container">
    <div class="dashboard-text">name: {{ name }}</div>
    333333
    <el-button type="primary" @click="btn">点击发送请求</el-button>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import axios from "axios";
export default {
  name: "Dashboard",
  computed: {
    ...mapGetters(["name"]),
  },
  methods: {
    async btn() {
      const { data: res } = await axios.post("http://localhost:3001/test", {
        name: "qq",
        password: "111",
      });
      console.log(res);
    },
  },
};
</script>

<style lang="less" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
