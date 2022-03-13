<template>
  <div>
    <p class="w3-large">
        <text-input :edit-view=editView label-title="Skill Evaluation Topic: "></text-input>
    </p>
    <div v-for="n in this.evaluationBoxCount" :key="n">
      <evaluation-box-item :edit-view=editView>
      </evaluation-box-item>
    </div>
    <br>
    <button v-if="editView" class="button" @click=addBox>Add Another Evaluation Item</button>
  </div>
</template>

<script>
import EvaluationBoxItem from '@/components/evaluationBox/EvaluationBoxItem'
import TextInput from '@/components/inputFields/TextInput'

export default {
  name: 'EvaluationBox',
  components: {TextInput, EvaluationBoxItem},
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    addBox: function () {
      this.evaluationBoxCount++
    }
  },
  data () {
    return {
      evaluationBoxCount: 1
    }
  }
}

</script>

<style scoped>
</style>
