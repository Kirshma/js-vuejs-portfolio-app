<template>
    <div>
       <span v-if="editView">
                            <img src="../../assets/logo.png" style="width:100%" alt="Avatar">
                            </span>
        <span v-if="!editView">
                            <img src="../../assets/avatar_hat.jpg" style="width:100%" alt="Avatar">
                                </span>
    </div>
</template>

<script>
export default {
  name: 'ImageInput',
  props: {
    editView: {
      type: Boolean,
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
