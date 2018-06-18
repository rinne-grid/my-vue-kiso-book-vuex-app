<template>
  <div class="edit-form">
    <input ref="input" v-bind:value="message" @input="doUpdate">
    <!-- <input v-model="message" /> -->
  </div>
</template>

<script>
import {
  // mapState,
  mapGetters
  // mapMutations,
  // mapActions
} from 'vuex'

export default {
  name: 'EditForm',
  computed: {
    // message() {
    //   return this.$store.getters.message
    // }
    // 算出プロパティにゲット・セットを登録し、storeのステートと画面の値をバインド
    // message: {
    //    get() { return this.$store.getter.message },
    //    set(value) { this.$store.dispatch('doUpdate', value) }
    // },
    ...mapGetters([
      'message'
    ])
  },
  methods: {
    doUpdate() {
      this.$store.dispatch('doUpdate', this.$refs.input.value)
    }
  }
}

</script>
