<template>
    <div>
        <i class="fa fa-calendar fa-fw w3-margin-right"></i>
        <span v-if=!editView>{{dateToBind1}}</span>
        <label v-if=editView for="dateInput1">{{this.labelTitle}}</label>
        <input v-if=editView v-model="dateToBind1" type="date" id="dateInput1" name="dateInput1" required minlength="1" > <!--maxlength="50000" size="100"-->
        <label for="dateInput2">until</label>
        <input v-if=editView v-model="dateToBind2" type="date" id="dateInput2" name="dateInput2" required minlength="1" >
        <span class="w3-tag w3-teal w3-round" v-if=!editView>{{dateToBind2}}</span>
    </div>
</template>

<script>
export default {
  name: 'DateInput',
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
