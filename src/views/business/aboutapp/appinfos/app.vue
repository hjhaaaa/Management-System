<template>   
   

<el-row>  
    <el-col>
        <el-card>
            <div>用户名：<span id="uname">{{dataname}}</span>
            </div>
            <div>用户名2：<span>{{language.fontTooltip}}</span>
            </div>
            <div>用户名3：<span>{{language.fontTooltip}}</span>
            </div>
        </el-card>
         <el-card>
            <div>用户名：<span>{{language.fontTooltip}}</span>
            </div>
        </el-card>
        
    </el-col>
     </el-row>
   
</template>
<script>
new Vue({
      el: '#uname',
        data: {
             dataname:"before"
        },
        created: function () {
　　　　　　//为了在内部函数能使用外部函数的this对象，要给它赋值了一个名叫self的变量。
            var self = this;
            $.ajax({
                url: 'www.taohuadao.club/api/app/logo',
                type: 'get',
                data: {},
                dataType: 'json'
            }).then(function (res) {
                console.log(res);
　　　　　　　　　　//把从json获取的数据赋值给数组
                self.dataname = res;
            }).fail(function () {
                console.log('失败');
            })
        }



    });
 export default {
        mixins : [ require ( "@/mymixins" ).default ] ,
        name : "buttonBasicUsage" ,
        data () {
            return {
                disabledTime : 3
            };
        } ,
    };
    
</script>
