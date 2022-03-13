<template>
  <div class="w3-twothird">
    <div class="w3-container w3-card w3-white w3-margin-bottom">
      <h2 class="w3-text-grey w3-padding-16"><i
        class="fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i><text-input :edit-view=editView label-title="Title/Topic: "></text-input></h2>
      <div v-for="n in this.timelineBoxCount" :key="n">
        <timeline-box-item :edit-view=editView></timeline-box-item>
      </div>
      <br>
      <button v-if="editView" class="button" @click=addBox>Add More Subtitles/Subtopics</button>
    </div>
  </div>
</template>

<script>
import TextInput from '@/components/inputFields/TextInput'
import TimelineBoxItem from '@/components/timelineBox/TimelineBoxItem'
export default {
  name: 'TimelineBox',
  components: {TimelineBoxItem, TextInput},
  props: {
    editView: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    addBox: function () {
      this.timelineBoxCount++
    }
  },
  data () {
    return {
      timelineBoxCount: 1
    }
  }
}
</script>

<style scoped>

</style>
