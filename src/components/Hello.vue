<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!--<button>Alert</button>-->
    <!--<a href="javascript:;" class="weui-btn weui-btn_warn" @click="onAlert">警告类操作 Normal</a>-->
    <a href="javascript:;" id='show-actions' class="weui_btn weui_btn_primary" @click="onDisplay">显示 ActionSheet</a>
    <a href="javascript:;" id='show-actions-bg' class="weui_btn weui_btn_primary">自定义背景色</a>
  </div>
</template>

<script>
  import weui from '../../static/js/weui.min.js'
  import $ from "jquery"

  export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    handleClickUploadList: function () {

    },
    onAlert: function () {
      weui.alert('alert');
    },
    onDisplay: function () {
      $.actions({
        title: "选择操作",
        onClose: function() {
          console.log("close");
        },
        actions: [
          {
            text: "发布",
            className: "color-primary",
            onClick: function() {
              $.alert("发布成功");
            }
          },
          {
            text: "编辑",
            className: "color-warning",
            onClick: function() {
              $.alert("你选择了“编辑”");
            }
          },
          {
            text: "删除",
            className: 'color-danger',
            onClick: function() {
              $.alert("你选择了“删除”");
            }
          }
        ]
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
