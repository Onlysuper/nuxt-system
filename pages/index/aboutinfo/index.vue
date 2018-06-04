<template>
  <div class="form-box">
    <el-form ref="form" :model="form" label-width="80px">
      <el-form-item label="名称">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="时间">
       <el-date-picker type="date" placeholder="选择日期" v-model="form.time" style="width: 100%;"></el-date-picker>
      </el-form-item>
      <el-form-item label="描述">
        <el-input type="textarea" v-model="form.useinto"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button>取消</el-button>
        <el-button type="primary" @click="onSubmit">确定</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
// import VueQuillEditor from '~/components/VueQuillEditor.vue'

export default {
  data(){
    return {
        form: {
          name: '',
          region: '',
          date1: '',
          date2: '',
          delivery: false,
          type: [],
          resource: '',
          desc: ''
        }
    }
  },
  methods:{
    onSubmit() {
      console.log('submit!');
    }
  },
  components: {
    // VueQuillEditor
  }
}
</script>

<style lang="scss" scoped>
.form-box{
  width: 600px;
}
</style>