<template>
  <div class="add-node-btn-box">
    <AddNodeBtn
      :node="node"
      @addnode="addnode"
    />
  </div>
</template>
<script>
import AddNodeBtn from './add-node-btn.vue'
export default {
  name: 'AddNodeBtnBox',
  emits:['addnode'],
  components: {
    AddNodeBtn
  },
  props: {
    node: {
      type: Object,
      default: undefined
    }
  },
  data: () => ({
  }),
  methods: {
    addnode (node) {
      this.$emit('addnode', node)
    }
  }
}
</script>
