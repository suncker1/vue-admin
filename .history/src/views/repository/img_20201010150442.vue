<template>
  <div>
    <el-upload
      ref="upload"
      :multiple="multiple"
      action="${pageContext.request.contextPath}/lookup/editEvidence/123"
      list-type="picture-card"
      :auto-upload="false"
      :http-request="uploadFile"
    >
      <i class="el-icon-plus" />
    </el-upload>
    <el-button @click="subPicForm">提交上传</el-button>
  </div>
</template>

<script>
export default {

  data() {
    return {
      multiple: true,
      formDate: ''
    }
  },

  methods: {
    uploadFile(file) {
      this.formDate.append('file', file.file)
      console.log(file.file)
      console.log(this.formDate.getAll('file'))
    },
    subPicForm() {
      this.formDate = new FormData()
      this.$refs.upload.submit()
      this.formDate.append('WS_CODE', '12133')
      // const config = {
      //   headers: {
      //     'Content-Type': 'multipart/form-data'
      //   }
      // }
      console.log(this.formDate.getAll('file'))
      // this.axios.post('your URL', this.formDate, config).then(res => {
      //   console.log(res)
      // }).catch(res => {
      //   console.log(res)
      // })
    }
  }
}
</script>
