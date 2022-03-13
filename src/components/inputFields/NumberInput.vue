<template>
  <div>
  <label v-if=editView for="numberInput">{{labelTitle}}</label>
  <input v-if=editView v-model="numberToBind" type="number" id="numberInput" name="number"
         min="10" max="100" required>
    <div class="w3-white w3-round-xlarge w3-small">
    <div v-if=!editView class="w3-container w3-center w3-round-xlarge w3-teal" v-bind:style="{width: format(numberToBind) + '%'} " >
      <div class="w3-center w3-text-white">{{formatWithNull(numberToBind)}}%</div>
    </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  },
  data () {
    return {
      labelTitle: 'Insert a number: (10-100): ',
      numberToBind: 0
    }
  },
  computed: {
    localState: {
      get () { return this.editView },
      set (editView) { this.$emit('input', editView) }
    }
  },
  methods: {
    format: function (numberToBind) {
      if (numberToBind > 100) {
        return 100
      } else if (numberToBind < 10) {
        return 10
      } else return numberToBind
    },
    formatWithNull: function (numberToBind) {
      if (numberToBind > 100) {
        return 100
      } else if (numberToBind < 10) {
        return 10
      } else if (numberToBind == null) {
        return 10
      } else return numberToBind
    }
  }
}
</script>

<style scoped>
</style>
