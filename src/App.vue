<template>
  <div id="app">
    <p>testList: {{testList}}</p>
    <p v-for="(item, key) in testList" :key="key">{{item}}</p>
    <el-dialog append-to-body v-show="dialogShow" :visible.sync="dialogShow">contentcontent</el-dialog>
    <p><el-button type="primary" @click="dialogShow = true">showDialog</el-button></p>
    <p><el-button @click="changeList">changeList</el-button></p>
    <p>bug step</p>
    <p>1. click "showDialog" button.</p>
    <p>2. close dialog.</p>
    <p>3. click "changeList" button.</p>
    <p>4. click "changeList" button again.</p>
    <p>(it's can be fixed like this)</p>
    <pre v-pre>&lt;div&gt;&lt;p v-for="(item, key) in testList" :key="key"&gt;{{item}}&lt;/p&gt;&lt;/div&gt;</pre>
    <p>(or like this)</p>
    <pre v-pre>&lt;div&gt;&lt;el-dialog append-to-body v-show="dialogShow" :visible.sync="dialogShow"&gt;contentcontent&lt;/el-dialog&gt;&lt;/div&gt;</pre>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      testList: [1, 2, 3, 4, 5, 6],
      dialogShow: false
    }
  },
  methods: {
    changeList () {
      console.log(this.testList = this.testList.length ? [] : [6, 5, 4, 3, 2, 1])
    }
  }
}
</script>
<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
</style>
