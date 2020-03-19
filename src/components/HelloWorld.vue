<template>
<div>
<input type="text" v-model="search">
<ul>
<!-- 注意！注意！注意！这里循环遍历的是items，不再是data里的list数组 -->
<li v-for="(item,index) in items">
<span>{{item.name}}</span>
<span>{{item.msg}}</span>
</li>
</ul>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
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
  computed: {
    items: function () {
      var _search = this.search

      if (_search) {
        var reg = new RegExp(_search, 'ig')

        return this.list.filter(function (e) {
          return Object.keys(e).some(function (key) {
            return e[key].match(reg)
          })
        })
      };
      return this.list
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
