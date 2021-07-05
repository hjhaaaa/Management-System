<template>
  <el-row>
    <div id="btn1">
      <button v-on:click="getme">点击</button>
      <el-col>
        <el-card>
          <div>
            用户名：<span>{{ test }}</span>
          </div>
          <div>
            用户名2：<span>{{ language.fontTooltip }}</span>
          </div>
          <div>
            用户名3：<span>{{ language.fontTooltip }}</span>
          </div>
        </el-card>
        <el-card>
          <div>
            用户名：<span>{{ language.fontTooltip }}</span>
          </div>
        </el-card>
      </el-col>
    </div>
  </el-row>
</template>

<script>
export default {
  mixins: [require("@/mymixins").default],

  name: "buttonBasicUsage",
  data() {
    return {
      disabledTime: 3,
      test: "aaa",
    };
  },
  methods: {
    getme: function () {
       var that=this
      //alert("click");
      this.$http
        .get("http://www.taohuadao.club/api/app/logo", {
          params: {
            word: "a",
          },
        })
        .then(
          function (res) {
           // alert(res.status);
            that.test=res.body;
            //console.log(res.data);
            //alert(res.data);

          },
          function (err) {
            alert("失败" + err.toString());
          }
        );
    },
  },
};
</script>
