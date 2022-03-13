<template>
  <div>
    <p><text-input :edit-view=editView label-title="Skill Evaluation Subtopic: "></text-input></p>
  <number-input :edit-view=editView></number-input>
  </div>
</template>

<script>
import TextInput from '@/components/inputFields/TextInput'
import NumberInput from '@/components/inputFields/NumberInput'

export default {
  name: 'EvaluationBoxItem',
  components: {NumberInput, TextInput},
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  },
  data () {
    return {
    }
  },
  computed: {
  },
  watch: {
    editView () {
      this.$emit('input', this.editView)
    }
  }
}
</script>

<style scoped>
</style>
