<template>
<el-container class="full-page">
  <!-- <vue-quill-editor></vue-quill-editor> -->
  <el-aside width="">
      <side-bar-menu :menuData="menuData" :isCollapse="isCollapse"></side-bar-menu>
  </el-aside>
  <el-container>
    <el-header>
      <el-radio-group v-model="isCollapse" style="margin-bottom: 20px;">
        <el-radio-button :label="false">展开</el-radio-button>
        <el-radio-button :label="true">收起</el-radio-button>
      </el-radio-group>
    </el-header>
    <el-main>
      <div style="display:flex">
       <el-table
        :data="tableData"
        border
        style="width: 100%" 
        height="100%">
        <el-table-column
          fixed
          prop="date"
          label="日期"
          width="150"
          >
        </el-table-column>
        <el-table-column
          prop="name"
          label="姓名"
          width="120">
        </el-table-column>
        <el-table-column
          prop="province"
          label="省份"
          width="120">
        </el-table-column>
        <el-table-column
          prop="city"
          label="市区"
          width="120">
        </el-table-column>
        <el-table-column
          prop="address"
          label="地址"
          width="300">
        </el-table-column>
        <el-table-column
          prop="zip"
          label="邮编"
          width="120">
        </el-table-column>
        <el-table-column
          fixed="right"
          label="操作"
          min-width="100px"
          >
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
            <el-button type="text" size="small">编辑</el-button>
          </template>
        </el-table-column>
      </el-table>
      </div>
    </el-main>
  </el-container>
</el-container>
</template>
<script>
import AppLogo from '~/components/AppLogo.vue';
import SideBarMenu from '~/components/SideBarMenu.vue';
import menuJson from '~/static/data/menu.json';
// import VueQuillEditor from '~/components/VueQuillEditor.vue'

export default {
  components: {
    AppLogo,
    SideBarMenu
    // VueQuillEditor
  },
   data() {
      return {
        menuData:menuJson,
        isCollapse: true,
        tableData: [{
          date: '2016-05-03',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }, {
          date: '2016-05-02',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }, {
          date: '2016-05-04',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }, {
          date: '2016-05-01',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }]
      };
    },
    methods: {
      
    }
}
</script>

<style>
.full-page{
  height: 100vh;
}
.table-main{
  width: 100%;
  height: 100%;
}
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }

  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    /* line-height: 200px; */
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
  }
  
  body > .el-container {
    /* margin-bottom: 40px; */
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
  }
  
  .el-container:nth-child(7) .el-aside {
  }
</style>
