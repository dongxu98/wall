<template>
  <div>
    <h1>kw33照片墙项目</h1>
    <ul class="wall">
      <li v-for="(item, index) in listimg" :key="index">
        <img :src="item" alt="" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["listimg"],
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
$color: red;
.wall {
  list-style: none;
  width: 1000px;
  min-height: 500px;
  margin: 50px auto;
  display: flex;
  flex-wrap: wrap;

  li {
    width: 230px;
    margin: 10px 10px;

    img {
      width: 100%;
      border: 1px solid $color;
      padding: 3px;
      border-radius: 5px;
    }
  }
}
</style>