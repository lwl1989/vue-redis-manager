<template>
  <div id="#app">
    <el-dialog
      :visible.sync="show_view"
      title="提示"
      width="30%">
      <el-form ref="form" :model="server" label-width="80px">
        <el-form-item label="主机">
          <el-input v-model="server.host"/>
        </el-form-item>
        <el-form-item label="端口">
          <el-input v-model="server.port"/>
        </el-form-item>
        <el-form-item label="密码">
          <el-input v-model="server.pwd"/>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="handleClose()">取 消</el-button>
        <el-button type="primary" @click="handleClose()">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: 'Server',
  data: function() {
    return {
      server: this.getDefaultServer(),
      show_view: false
    }
  },
  methods: {
    handleClose() {
        this.show_view = false
    },
    show(server) {
      this.server.host = server.host
      this.server.port = server.port
      this.server.pwd = server.pwd
      this.show_view = true
    },
    save(index) {
      // todo: do ajax
    },
    getDefaultServer() {
      return {
        host: '',
        port: '',
        pwd: ''
      }
    }
  }
}
</script>

<style scoped>

</style>
