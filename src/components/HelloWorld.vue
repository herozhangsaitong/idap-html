<template>
<div>

  <span>
    1203785956
  </span>
<!-- <input type="text" v-model="search"> -->
<!-- <ul>
<li v-for="item in items" :key="item">
<span>{{item.name}}</span>
<span>{{item.msg}}</span>
</li>
</ul> -->
<!-- <input type="text" v-model="asd">
<button @click="index"> 提交 </button> -->
   <select size="mini" @change="asd" v-model="chag">
          <option
           v-for="(value, index) in DataTypeName"
           :key="index"
           :label="value"
           :value="value"
         >
         </option>
      </select>
<div ref="imageWrapper">
      <div class="success">
        <div class="img">
          <img class="img-icon" src="../assets/logo.png"/>
          <p style="font-weight: 600; font-size: 18px">支付成功</p>
        </div>
      </div>
      <div class="success-detail">
        <el-row style="margin-top: 10px;">
          <el-col :span="5" class="col-left-suc">收款商家</el-col>
          <el-col :span="16" class="col-right">{{merchant}}</el-col>
        </el-row>
        <el-row style="margin-top: 10px;">
          <el-col :span="5" class="col-left-suc">费用名称</el-col>
          <el-col :span="16" class="col-right">{{contName}}</el-col>
        </el-row>
        <el-row style="margin-top: 10px;">
          <el-col :span="5" class="col-left-suc">缴费金额</el-col>
          <el-col :span="16" class="col-right">{{chargePrice}}元</el-col>
        </el-row>
      </div>
    </div>
    <div class="button">
      <el-button style="width: 70%;" type="success" size="small" @click="toImage">生成截图</el-button>
    </div>

</div>
</template>
<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      chag: null,
      asd: '',
      DataTypeName: {0: '数值', 1: '字符', 2: '日期'},
      search: '',
      list: [
        {name: 'AAA', msg: 'aaa文本介绍1'},
        {name: 'BBB', msg: 'bbb文本介绍2'},
        {name: 'CCC', msg: 'ccc文本介绍3'},
        {name: 'DDD', msg: 'ddd文本介绍4'},
        {name: 'EEE', msg: 'eee文本介绍5'}
      ]
    }
  },
  methods: {

    // toImage () {
    //   html2canvas(this.$refs.imageWrapper).then(canvas => {
    //     let dataURL = canvas.toDataURL('image/png')
    //     this.imgUrl = dataURL
    //     if (this.imgUrl !== '') {
    //       this.dialogTableVisible = true
    //     }
    //   })
    // }

    // index () {
    //   let regx = /((2(5[0-5]|[0-4]\d))|[0-1]?\d{1,2})(\.((2(5[0-5]|[0-4]\d))|[0-1]?\d{1,2})){3}:([0-9]|[1-9]\d{1,3}|[1-5]\d{4}|6[0-5]{2}[0-3][0-5])/g
    //   // let asds = new RegExp(regx, 'g')
    //   let debugg = this.asd
    //   console.log(regx.test(debugg))
    //   // debugg.search(regx) ? console.log(debugg) : console.log('0000000')
    //   // regx.test(this.asd) ? console.log(this.asd) : console.log('0000000')
    //   // console.log(this.asd.search(regx))
    //   // let reg = /^((25[0-5]|2[0-4]\\d|[1]{1}\\d{1}\\d{1}|[1-9]{1}\\d{1}|\\d{1})($|(?!\\.$)\\.)){4}:([0-9]|[1-9]\d{1,3}|[1-5]\d{4}|6[0-5]{2}[0-3][0-5])$/
    //   // let ab = this.asd
    //   // eslint-disable-next-line eqeqeq
    //   // if (regx.test(this.asd) == true) {
    //   //   return console.log(this.asd)
    //   // } else {
    //   //   return console.log('11111')
    //   // }
    // }
  },
  computed: {
    asd: function () {
      console.log(this.chag)
    }
    // items: function () {
    //   var _search = this.search

    //   if (_search) {
    //     var reg = new RegExp(_search, 'ig')

    //     return this.list.filter(function (e) {
    //       return Object.keys(e).some(function (key) {
    //         return e[key].match(reg)
    //       })
    //     })
    //   };
    //   return this.list
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.xibao_wrapper {
        width: 100%;
        height: 100%;
        position: fixed;
        left: 0;
        top: 0;
        z-index: -1;
 }
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
