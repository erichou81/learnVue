<template id="aid">
  <div class="d2" v-on:click="s">
    <img v-bind:src="im" style="height: 40px; width: 60px" v-if="show" />
  </div>
</template>
<style>
.d2 {
  width: 60px;
  height: 40px;
  background-color: pink;
  display: inline-block;
}
</style>
<script type="text/javascript">

    // import MyComponentTemplate from './BattleroidLayout.vue';
    //vue自定义构建组件
    Vue.component("a-div", {
      //模板位置
      template: "#a-id",
      //父组件向子组件传递内容
      props: ["im"],

      data: function () {
        return {
          show: true,
        };
      },
      //根据调用的方法v-on:click="s"和属性v-if="show"显示隐藏
      methods: {
        s: function () {
          this.show = !this.show;
        },
      },
    });
    var app = new Vue({
      el: "#app",
      data: {
        imgg: [
          "images-BMW/宝马_01.gif",
          "images-BMW/宝马_02.gif",
          "images-BMW/宝马_03.gif",
          "images-BMW/宝马_04.gif",
          "images-BMW/宝马_05.jpg",
          "images-BMW/宝马_06.gif",
          "images-BMW/宝马_07.gif",
          "images-BMW/宝马_08.gif",
          "images-BMW/宝马_09.gif",
          "images-BMW/宝马_10.gif",
          "images-BMW/宝马_11.gif",
          "images-BMW/宝马_12.gif",
          "images-BMW/宝马_13.gif",
          "images-BMW/宝马_14.gif",
          "images-BMW/宝马_15.gif",
          "images-BMW/宝马_16.gif",
        ],
      },
    });
  </script>