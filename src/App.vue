<template>
    <h4>个人信息</h4>
    <h6 v-show="person.name">姓名:{{ person.name }}</h6>
    <h6>年龄:{{ person.age }}</h6>
    <h6 v-show="person.sex">性别:{{ person.sex }}</h6>
    <h6>岗位:{{ person.job.type }}</h6>
    <h6>薪资:{{ person.job.salary }}</h6>
    <h6>爱好:{{ person.hobby }}</h6>
    <button @click="sayHello">自我介绍</button>
    <button @click="updateInfo">更新数据</button>
    <button @click="addSex">添加性别</button>
    <button @click="delName">删除姓名</button>
</template>

<script>
import { reactive } from "vue";
export default {
    name: "App",
    setup() {
        let person = reactive({
            name: "张三",
            age: 22,
            job: {
                type: "python开发",
                salary: "30K",
            },
            hobby: ["吃饭", "睡觉", "玩游戏"],
        });

        function sayHello() {
            alert(`my name is ${person.name}, age is ${person.age}`);
        }

        function updateInfo() {
            person.name = "李四";
            person.age = 44;
            person.job.type = "golang开发";
            person.job.salary = "50k";
            person.hobby[2] = "喝水";
        }
        function addSex() {
            person.sex = "男";
        }
        function delName() {
            delete person.name;
        }
        return {
            person,
            sayHello,
            updateInfo,
            addSex,
            delName,
        };
    },
};
</script>

