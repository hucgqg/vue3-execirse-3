<template>
    <h4>个人信息</h4>
    <h6>姓名:{{ name }}</h6>
    <h6>年龄:{{ age }}</h6>
    <h6>test1:{{ job.type.test1 }}</h6>
    <h6>test2:{{ job.type.test2 }}</h6>
    <button @click="sayHello">自我介绍</button>
    <button @click="updateInfo">更新数据</button>
</template>

<script>
import { ref } from "vue";
export default {
    name: "App",
    setup() {
        let name = ref("xtdg");
        let age = ref(44);
        let job = ref({
            type: {
                test1: "test1",
                test2: "test2",
            },
            mony: "33k",
        });

        function sayHello() {
            alert(`my name is ${name}, age is ${age}`);
        }

        function updateInfo() {
            name.value = "李四";
            age.value = 22;
            job.value.type.test1 = "test11";
            job.value.type.test2 = "33333";
            console.log(name, age);
            console.log(job.value);
        }
        return {
            name,
            age,
            job,
            sayHello,
            updateInfo,
        };
    },
};
</script>

