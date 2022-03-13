<template>
  <div>
  <span v-if=!editView>{{textToBind}}</span>
    <label v-if=editView for="textInput">{{this.labelTitle}}</label>
    <input v-if=editView v-model="textToBind" type="text" id="textInput" name="textInput" required minlength="1" > <!--maxlength="50000" size="100"-->
  </div>
</template>

<script>
export default {
  name: 'TextInput',
  props: {
    editView: {
      type: Boolean,
      required: true
    },
    labelTitle: {
      type: String,
      required: true
    }
  },
  computed: {
  },
  data () {
    return {
      textToBind: ''
    }
  },
  methods: {
  }
}
</script>

<style scoped>
</style>
