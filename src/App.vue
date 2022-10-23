<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="common-layout">
    <el-container>
      <el-header class="header">
        <RouterLink to="/">一个简单的ToDoList</RouterLink>
      </el-header>
      <el-main>
        <RouterView />
      </el-main>
      <el-footer class="footer">页脚</el-footer>
    </el-container>
  </div>
</template>


<style scoped>

.el-container{
  min-height: 100vh;
}

.header{
  text-align: center;
  line-height: 50px;
  height: 50px;
  background-color: #409EFF;
}

.footer{
  text-align: center;
  line-height: 50px;
  height: 50px;
  background-color: #409EFF;
}
</style>