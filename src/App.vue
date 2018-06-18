<template>
  <div id="app">
    <p>{{ message }}</p>
    <edit-form></edit-form>
  </div>
</template>

<script>
import EditForm from '@/components/EditForm'

export default {
  name: 'App',
  created() {
    console.log('storeの状態---|')
    console.log(this.$store.state.count)
  },
  computed: {
    message() { return this.$store.getters.message }
  },
  components: {
    EditForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
