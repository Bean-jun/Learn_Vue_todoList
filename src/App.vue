<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">一个简单的ToDoList</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<style scoped>
nav{
  position: absolute;
  line-height: 30px;
  background-color: rgb(0, 0, 0);
  top: 0px;
  left: 0px;
  right: 0px;
}
nav {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
nav > a{
  width: 33%;
  color: aliceblue;
  text-align: center;
}
</style>