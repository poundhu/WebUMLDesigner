<template>
    <div id="main">
        <div id="head">
            <el-menu
                :default-active="activeIndex"
                class="el-menu-demo"
                mode="horizontal"
                @select="handleSelect"
            >
                <el-menu-item index="1">个人</el-menu-item>
                <el-menu-item index="2">团队</el-menu-item>
            </el-menu>
        </div>
        <div v-if="activeIndex == '1'">
            <PersonalPanel></PersonalPanel>
            <!--
            <div id="other">
                <div id="left">
                    <el-button id="newfile" @click="newfile()" type="primary">新建文件</el-button>
                </div>
                <div id="right">
                    <p>我的文件:</p>
                    <div id="files">
                        <div id="file0">
                            <img :src="file0" id="pic0" />
                            <p id="filename0">文件0</p>
                        </div>
                        <div id="file1">
                            <img :src="file1" id="pic1" />
                            <p id="filename1">文件1</p>
                        </div>
                        <div id="file2">
                            <img :src="file2" id="pic2" />
                            <p id="filename2">文件2</p>
                        </div>
                        <div id="file3">
                            <img :src="file3" id="pic3" />
                            <p id="filename3">文件3</p>
                        </div>
                        <div id="file4">
                            <img :src="file4" id="pic4" />
                            <p id="filename4">文件4</p>
                        </div>
                        <div id="file5">
                            <img :src="file5" id="pic5" />
                            <p id="filename5">文件5</p>
                        </div>
                        <div id="file6">
                            <img :src="file6" id="pic6" />
                            <p id="filename6">文件6</p>
                        </div>
                    </div>
                </div>
            </div>
            -->
        </div>
        <div v-else>
            <GroupPanel></GroupPanel>
        </div>
    </div>
</template>

<script>
import GroupPanel from "../views/mainpage/GroupPanel.vue";
import PersonalPanel from "../views/mainpage/PersonalPanel.vue";
export default {
    name: "personal-page",
    components: {
        GroupPanel,
        PersonalPanel
    },
    data() {
        return {
            activeIndex: "1",
            file0: require("../assets/file0.png"),
            file1: require("../assets/file0.png"),
            file2: require("../assets/file0.png"),
            file3: require("../assets/file0.png"),
            file4: require("../assets/file0.png"),
            file5: require("../assets/file0.png"),
            file6: require("../assets/file0.png"),
        };
    },
    methods: {
        handleSelect(key, keyPath) {
            this.activeIndex = key;
        },
    }
};
</script>

<style scoped>
#main {
    width: 100%;
}
#head {
    width: 100%;
    height: 60px;
}
#username {
    position: absolute;
    left: 5%;
    display: inline;
}
#other {
    background-color: #ccc;
}
#left {
    width: 20%;
    height: 100%;
    display: inline;
    background-color: #ccc;
    position: fixed;
    left: 0;
}
#right {
    width: 80%;
    height: 100%;
    display: inline;
    background-color: #ccc;
    position: fixed;
    left: 20%;
}
#newfile {
    display: block;
    position: fixed;
    width: 150px;
    height: 30px;
    border: 1px;
    padding: 5px 20px;
    margin: 20px 20px;
    font-size: 14px;
    outline: none;
}
#files {
    width: 100%;
    height: auto;
}
#file0 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file1 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file2 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file3 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file4 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file5 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#file6 {
    display: inline-block;
    width: 15%;
    height: auto;
    padding: 5px 5px;
    margin: 2% 2%;
    font-size: 14px;
    outline: none;
    background-color: dodgerblue;
}
#pic0 {
    width: 100%;
    display: block;
}
#filename0 {
    text-align: center;
}
#pic1 {
    width: 100%;
    display: block;
}
#filename1 {
    text-align: center;
}
#pic2 {
    width: 100%;
    display: block;
}
#filename2 {
    text-align: center;
}
#pic3 {
    width: 100%;
    display: block;
}
#filename3 {
    text-align: center;
}
#pic4 {
    width: 100%;
    display: block;
}
#filename4 {
    text-align: center;
}
#pic5 {
    width: 100%;
    display: block;
}
#filename5 {
    text-align: center;
}
#pic6 {
    width: 100%;
    display: block;
}
#filename6 {
    text-align: center;
}
</style>