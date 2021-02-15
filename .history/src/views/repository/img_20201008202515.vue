<template>
  <div>
    <el-upload
      :action="action"
      multiple
      :http-request="modeUpload"
    >
      <el-button size="small" type="primary">点击上传</el-button>
    </el-upload>
    <el-button @click="upload">点击上传文件</el-button>
  </div>
</template>

<script>
export default {

  data() {
    return {
      action: 'https://jsonplaceholder.typicode.com/posts/',
      mode: {}
    }
  },

  methods: {
    upload: function() {
      const fd = new FormData()
      fd.append('templateFile', this.mode)
      // eslint-disable-next-line no-undef
      // axios.post('/api/reportRule', fd, {
      //   headers: {
      //     'Content-Type': 'multipart/form-data'
      //   }
      // }).then(response => {
      //   console.log(response.data)
      // })
    },
    modeUpload: function(item) {
      console.log(item.file)
      this.mode = item.file
    }
  }
}
</script>
