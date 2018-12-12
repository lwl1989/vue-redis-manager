<template>
    <div>
        left menu
    </div>
</template>

<script>
export default {
  name: 'Server',
  data: function () {
    return this.getDefaultServer()
  },
  methods: {
    show (server) {
      this.host = server.host
      this.port = server.port
      this.pwd = server.pwd
    },
    save (index) {
      // todo: do ajax
    },
    getDefaultServer () {
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
