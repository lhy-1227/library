<template>
  <div class="manage">
    <el-input v-model="input" placeholder="请输入书籍名称" class="input"></el-input>
    <el-row>
      <el-button type="primary" class="found1" >搜索</el-button>
      <el-button type="primary" @click="addVisible = true" class="found">添加书籍</el-button>
      <el-button type="primary" class="found">删除书籍</el-button>
      <el-button type="primary" @click="updateVisible = true" class="found">修改书籍</el-button>
      <el-button type="primary" @click="addCotaVisible = true" class="found">添加书籍类别</el-button>
      <el-button type="primary" class="found">删除书籍类别</el-button>
    </el-row>

     <el-dialog title="添加书籍" :visible.sync="addVisible">
        <el-form :model="form">
          <el-form-item label="书籍编号" :label-width="formLabelWidth">
            <el-input v-model="form.id" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍名称" :label-width="formLabelWidth">
            <el-input v-model="form.name" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍出版社" :label-width="formLabelWidth">
            <el-input v-model="form.publish" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍发布者" :label-width="formLabelWidth">
            <el-input v-model="form.publisher" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
        </el-form>
        <div slot="footer" class="dialog-footer">
          <el-button @click="dialogFormVisible = false">取 消</el-button>
          <el-button type="primary" @click="dialogFormVisible = false">添加</el-button>
        </div>
      </el-dialog>

      <el-dialog title="添加书籍类别" :visible.sync="addCotaVisible">
        <el-form :model="form">
          <el-form-item label="书籍类别" :label-width="formLabelWidth">
            <el-input v-model="form.id" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
        </el-form>
        <div slot="footer" class="dialog-footer">
          <el-button @click="addCotaVisible = false">取 消</el-button>
          <el-button type="primary" @click="addCotaVisible = false">添加</el-button>
        </div>
      </el-dialog>

      <el-dialog title="修改书籍" :visible.sync="updateVisible">
        <el-form :model="form">
          <el-form-item label="书籍编号" :label-width="formLabelWidth">
            <el-input v-model="form.id" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍名称" :label-width="formLabelWidth">
            <el-input v-model="form.name" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍出版社" :label-width="formLabelWidth">
            <el-input v-model="form.publish" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
          <el-form-item label="书籍发布者" :label-width="formLabelWidth">
            <el-input v-model="form.publisher" autocomplete="off" class="addinput"></el-input>
          </el-form-item>
        </el-form>
        <div slot="footer" class="dialog-footer">
          <el-button @click="updateVisible = false">取 消</el-button>
          <el-button type="primary" @click="updateVisible = false">确认修改</el-button>
        </div>
      </el-dialog>


      <el-table
        ref="filterTable"
        :data="tableData"
        class="table">
        <el-table-column
          prop="id"
          label="书籍编号"
          width="180">
        </el-table-column>
        <el-table-column
          prop="name"
          label="书籍名称"
          width="180">
        </el-table-column>
        <el-table-column
          prop="publish"
          label="书籍出版社"
          width="180">
        </el-table-column>
        <el-table-column
          prop="publisher"
          label="书籍发布者"
          width="180">
        </el-table-column>
        <el-table-column
          prop="category"
          label="书籍类别"
          sortable
          width="180"
          column-key="category"
          :filters="[{text: '2016-05-01', value: '2016-05-01'}, {text: '2016-05-02', value: '2016-05-02'}, {text: '2016-05-03', value: '2016-05-03'}, {text: '2016-05-04', value: '2016-05-04'}]"
          :filter-method="filterHandler"
        >
        </el-table-column>
      </el-table>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  data() {
    return {
      input: '',
      addVisible: false,
      updateVisible: false,
      addCotaVisible: false,
      form: {
        id: '',
        name: '',
        publish: '',
        publisher: ''
      },
      formLabelWidth: '150px',
      tableData: [{
        id: '0',
        category: '2016-05-02',
        name: '王小虎',
        publish: '上海市普陀区金沙江路 1518 弄',
        publisher: '家'
      }, {
        id: '0',
        category: '2016-05-02',
        name: '王小虎',
        publish: '上海市普陀区金沙江路 1518 弄',
        publisher: '家'
      }, {
        id: '0',
        category: '2016-05-03',
        name: '王小虎',
        publish: '上海市普陀区金沙江路 1518 弄',
        publisher: '家'
      }, {
       id: '0',
        category: '2016-05-01',
        name: '王小虎',
        publish: '上海市普陀区金沙江路 1518 弄',
        publisher: '家'
      }]
    }
  },
  methods: {
    filterHandler(value, row, column) {
      const property = column['property'];
      return row[property] === value;
    }
  }
}
</script>

<style lang="scss" scoped>
  .manage {
    margin-top: 2%;
  }
  .input {
    width: 200px;
    margin-left: 2%;
  }
  .found1 {
    position: relative;
    bottom: 40px;
    left: 250px;
    margin-right: 8%;
  }
  .found {
    position: relative;
    bottom: 40px;
    left: 250px;
  }
  .addinput {
    width: 400px;
  }
  .table {
    margin-left: 2%;
  }
</style>
