<template>
    <div class="form-area">
        名前： <input v-model="user"><br>
        コメント：  <textarea v-model="message"></textarea><br>
        <button v-on:click="doAdd">書き込む</button>
    </div>
</template>

<script>
export default {
  name: 'BordForm',
  data () {
    return {
      user: '',
      message: ''
    }
  },
  methods: {
    doAdd () {
      this.$emit('input', this.user, this.message)
    }
  }
}
</script>
