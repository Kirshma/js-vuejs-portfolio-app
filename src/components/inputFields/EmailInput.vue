<template>
    <div>
        <span v-if=!editView>{{textToBind}}</span>
        <label v-if=editView for="textInput">{{this.labelTitle}}</label>
        <input v-if=editView v-model="textToBind" type="email" id="textInput" name="textInput" required minlength="1" >
    </div>
</template>

<script>
export default {
  name: 'EmailInput',
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
