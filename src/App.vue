<template>
  <div id="app">
    <PhotoWall :listimg="myimg" />
  </div>
</template>

<script>
import PhotoWall from "./components/PhotoWall.vue";
import axios from 'axios'
export default {
  name: "App",
  components: {
    PhotoWall,
  },
  data() {
    return {
      myimg: [],
    };
  },
  created () {
    // 使用在线mockjs生成的接口：https://www.fastmock.site/mock/4f60d566644d6646e94d679ea86f9287/aixue8/zpq
    // 使用node+mockjs生成的接口：http://127.0.0.1:3000/getphoto
      axios.get('https://www.fastmock.site/mock/4f60d566644d6646e94d679ea86f9287/aixue8/zpq')
      .then(res => {
        console.log(res.data.list)
        res.data.list.forEach(item => {
          this.myimg.push(item.src)
        })
      })
    },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>
