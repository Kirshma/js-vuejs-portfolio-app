<template>
  <div>
    <p>
      <i class="fa fa-briefcase fa-fw w3-margin-right w3-large w3-text-teal"></i>
      <text-input label-title="Profession Title: " :edit-view=editView ></text-input>
    </p>
    <p>
      <i class="fa fa-home fa-fw w3-margin-right w3-large w3-text-teal"></i>
      <text-input label-title="Residence: " :edit-view=editView></text-input>
    </p>
    <p>
      <i class="fa fa-envelope fa-fw w3-margin-right w3-large w3-text-teal"></i>
      <email-input label-title="Email: " :edit-view=editView></email-input>
    </p>
    <p>
      <i class="fa fa-phone fa-fw w3-margin-right w3-large w3-text-teal"></i>
      <text-input label-title="Phone Number: " :edit-view=editView></text-input>
    </p>
  </div>
</template>

<script>
import TextInput from '@/components/inputFields/TextInput'
import EmailInput from '@/components/inputFields/EmailInput'
export default {
  name: 'BasicInfoBox',
  components: { EmailInput, TextInput },
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  }
}

</script>

<style scoped>

</style>
