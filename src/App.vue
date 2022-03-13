<template>
    <!DOCTYPE html>
    <div>
        <title>W3.CSS Template</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
        <link rel='stylesheet' href='https://fonts.googleapis.com/css?family=Roboto'>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
        <body class="w3-light-grey">
        <button class="button" @click="toggle">Toggle Edit View</button>
        <!-- Page Container -->
        <div class="w3-content w3-margin-top" style="max-width:1400px;">
            <!-- The Grid -->
            <div class="w3-row-padding">
                <!-- Left Column -->
                <div class="w3-third">
                    <div class="w3-white w3-text-grey w3-card-4">
                        <div class="w3-display-container">
                            <!-- <image-input>-->
                            <ImageInput :edit-view=editView></ImageInput>
                            <div class="w3-display-bottomleft w3-container w3-text-black">
                                <h2>{{text}}</h2>
                            </div>
                        </div>
                        <div class="w3-container">
                            <span v-if="editView">Your Name: <input type="text" v-model="text" style="max-width: 100%"></span>
                            <basic-info-box :edit-view=editView></basic-info-box>
                            <hr/>
                            <div v-for="n in this.evaluationBoxCount" :key="n">
                            <evaluation-box :edit-view=editView></evaluation-box>
                            </div>
                          <br>
                            <button v-if="editView" class="button" @click=addBoxEval>Add Another Evaluation Box</button>

                            <br>
                        </div>
                    </div>
                    <!-- End Left Column -->
                </div>
                <!-- Right Column -->
                <div class="w3-twothird">
                    <div class="w3-container">
                    <button v-if="editView" class="button" @click=addBox>Add Another Topic</button>
                    <div v-for="n in this.timelineBoxCount" :key="n">
                        <timeline-box :edit-view=editView></timeline-box>
                    </div>
                    </div>
                    <!-- End Right Column -->
                </div>
                <!-- End Grid -->
            </div>
            <!-- End Page Container -->
        </div>
        </body>
    </div>
</template>

<script>
import EvaluationBox from '@/components/evaluationBox/EvaluationBox'
import Footer from '@/components/footer/Footer'
import TimelineBox from '@/components/timelineBox/TimelineBox'
import BasicInfoBox from '@/components/basicInfoBox/BasicInfoBox'
import ImageInput from '@/components/inputFields/ImageInput'

export default {
  methods: {
    toggle: function () {
      this.editView = !this.editView
    },
    addBox: function () {
      this.timelineBoxCount++
    },
    addBoxEval: function () {
      this.evaluationBoxCount++
    }
  },
  data () {
    return {
      editView: true,
      timelineBoxCount: 1,
      evaluationBoxCount: 1
    }
  },
  props: {
    text: String
  },
  components: {BasicInfoBox, TimelineBox, EvaluationBox, Footer, ImageInput}
}
</script>

<style>
    .button {
        -webkit-transition-duration: 0.4s; /* Safari */
        transition-duration: 0.4s;
        background-color: white;
        color: gray;
        border: none;
        height: 40px;
    }

    .button:hover {
        box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 0.24), 0 17px 50px 0 rgba(0, 0, 0, 0.19);
    }
</style>
