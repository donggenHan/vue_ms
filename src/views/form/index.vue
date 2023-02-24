<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="活动名称">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="地点">
        <el-select v-model="form.region" placeholder="please select your zone">
          <el-option label="上海" value="shanghai" />
          <el-option label="北京" value="beijing" />
        </el-select>
      </el-form-item>
      <el-form-item label="时间">
        <el-col :span="11">
          <el-date-picker v-model="form.date1" type="date" placeholder="选择一个日期" style="width: 100%;" />
        </el-col>
        <el-col :span="2" class="line">-</el-col>
        <el-col :span="11">
          <el-time-picker v-model="form.date2" type="fixed-time" placeholder="选择一个时间" style="width: 100%;" />
        </el-col>
      </el-form-item>
      <el-form-item label="按钮">
        <el-switch v-model="form.delivery" />
      </el-form-item>
      <el-form-item label="类型">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="线上活动" name="type" />
          <el-checkbox label="远距离活动" name="type" />
          <el-checkbox label="线下活动" name="type" />
          <el-checkbox label="简单活动" name="type" />
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="资源">
        <el-radio-group v-model="form.resource">
          <el-radio label="1" />
          <el-radio label="2" />
        </el-radio-group>
      </el-form-item>
      <el-form-item label="其他">
        <el-input v-model="form.desc" type="textarea" />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Create</el-button>
        <el-button @click="onCancel">Cancel</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
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
  methods: {
    onSubmit() {
      this.$message('submit!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
        type: 'warning'
      })
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
</style>

