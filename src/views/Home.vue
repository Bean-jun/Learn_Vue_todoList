<script setup>
import { ref } from 'vue';
import {
    Check,
    Delete,
    Edit,
} from '@element-plus/icons-vue'

const inputVal = ref("");
const TodoList = ref([
    "ToDo: 1",
    "ToDo: 2",
    "ToDo: 3",
]);
const Index = ref(-1);

function commit(index) {
    console.log("[log]" + index, + inputVal.value);
    // 用户添加表单时的操作
    if (index == -1) {
        if (inputVal.value === "") {
            alert("请输入内容后提交");
            return
        }
        TodoList.value.push(inputVal.value);
        inputVal.value = "";
    };
    // 用户修改下方数据时的操作
    if (index != -1) {
        if (inputVal.value === "") {
            alert("请输入内容后提交");
            return
        }
        TodoList.value.splice(index, 1, inputVal.value);
        inputVal.value = "";
        Index.value = -1;
    };
}

function editElem(elementId) {
    inputVal.value = TodoList.value[elementId];
    Index.value = elementId;
}

function deleteElem(elementId) {
    TodoList.value.splice(elementId, 1);
}
</script>

<template>
    <div class="continer">
        <form action="#">
            <el-input class="input" v-model="inputVal" placeholder="请输入" name="log" />
            <el-button class="input" @click="commit(Index)" type="success" :icon="Check" circle />
        </form>
        <div class="todo-content" v-for="item in TodoList">
            <ul>
                <li>{{ item }}</li>
                <el-button @click="editElem(TodoList.indexOf(item))" type="primary" :icon="Edit" />
                <li>
                    <el-button @click="deleteElem(TodoList.indexOf(item))" type="primary" :icon="Delete" />
                </li>
            </ul>
        </div>
    </div>
</template>


<style scoped>
.continer {
    margin-top: 70px;
    display: flex;
    flex-direction: column;
    align-items: center
}

.continer .input {
    display: inline;
    margin: 0px 10px;
}

.continer ul {
    padding-left: 0px;
    margin-top: 40px;
    display: flex;
    flex-direction: row;
    align-items: center
}

.continer ul li {
    padding: 0px 10px;
}


#log {
    margin-right: 10px;
}

.todo-content {
    margin-top: 20px;
}
</style>