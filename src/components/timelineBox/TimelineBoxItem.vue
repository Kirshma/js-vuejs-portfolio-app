<template>
  <div class="w3-container">
    <hr>
    <h5 class="w3-opacity"><b><text-input :edit-view=editView label-title="Subtitle/Subtopic: "></text-input></b></h5>
    <h6 class="w3-text-teal"><date-input :edit-view=editView label-title="Date from..."></date-input></h6>
    <h6 class="w3-text-grey w3-padding-16">
      <text-input :edit-view=editView label-title="Description: "></text-input></h6>

  </div>
</template>

<script>
import TextInput from '@/components/inputFields/TextInput'
import DateInput from '../inputFields/DateInput'
export default {
  name: 'TimelineBoxItem',
  components: {DateInput, TextInput},
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>

</style>
