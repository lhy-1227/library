<template>
  <div>
    <el-select v-model="value1" multiple placeholder="请选择" class="box">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
      </el-option>
    </el-select>
    <el-row class="foundbutton">
      <el-button type="primary">搜索</el-button>
    </el-row>
    <div class="book">
      <div style="margin-bottom:2%">图书信息</div>
      <div class="bookinfo">
        <el-card :body-style="{ padding: '0px' }" v-for="o in 6" :key="o" class="card">
          <router-link to="/book"><img src="http://pic.baike.soso.com/ugc/baikepic2/10627/cut-20180126140506-1981945355_jpg_1275_1594_97635.jpg/300" class="image"></router-link>
          <div style="padding: 14px;text-align: center;0">
            <span>红楼梦</span>
          </div>
        </el-card>
      </div>
    </div>
    <el-pagination
      background='true'
      layout="prev, pager, next"
      :total="1000"
      class="button">
    </el-pagination>
  </div>
</template>

<script>
export default {
  data() {
      return {
        options: [{
          value: '选项1',
          label: '文学'
        }, {
          value: '选项2',
          label: '自然科学'
        }, {
          value: '选项3',
          label: '哲学'
        }, {
          value: '选项4',
          label: '外国文学'
        }],
        value1: [],
        value2: []
        }
      }
}
</script>

<style scoped>
.box {
  margin-left: 7%;
  margin-top: 2%;
}
.foundbutton {
   position: relative;
   bottom: 40px;
   left: 300px;
}
.book {
  margin-left: 7%;
  margin-top: 2%;
}
  .bookinfo {
    display: flex;
    flex-wrap: wrap;
  }
    .card {
      margin-right: 9%;
      margin-bottom: 2%;
    }
    .image {
      width: 100%;
      display: block;
    }
  .button {
     margin-left: 53%;
     margin-bottom: 2%;
  }
</style>


