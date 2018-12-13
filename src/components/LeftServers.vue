<template>
  <div>
    <Server ref="server"/>
  </div>
</template>

<script>
import Server from './Server'
export default {
  name: 'LeftServers',
  components: { Server },
  data: function() {
    return {
      servers: []
    }
  },
  methods: {
    addServer(host, port, pwd) {
      this.servers.push({ host: host, port: port, pwd: pwd })
    },
    delServer(index) {
      if (this.servers.length > index) {
        this.servers = this.servers.slice(0, index).concat(this.servers.slice(index + 1, this.length))
      } else {
        if (this.servers.length === index) {
          this.servers = this.servers.slice(0, index - 1)
        } else {
          // todo: warning
        }
      }
    },
    editServer(index, host, port, pwd) {
      const server = this.get(index)
      this.$refs.server.show(server)
    },
    get(index) {
      if (index > this.servers.length) {
        return this.$refs.server.getDefaultServer()
      } else {
        return this.servers[index]
      }
    }
  }
}
</script>

<style scoped>

</style>
