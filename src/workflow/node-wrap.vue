<template>
  <div className="node-wrap">
    <NodeWrapBox
        :node="node"
        @delNode="delNode"
    />
    <AddNodeBtnBox
        :node="node"
        @addnode="addnode"
    />
  </div>
</template>
<script>
import NodeWrapBox from './node-wrap-box.vue'
import AddNodeBtnBox from './add-node-btn-box.vue'

export default {
  name: 'NodeWrap',
  emits:['addnode','delNode'],
  components: {
    NodeWrapBox,
    AddNodeBtnBox
  },
  props: {
    node: {
      type: Object,
      default: undefined
    }
  },
  methods: {
    addnode(node) {
       console.log('node-wrap 新节点:')
       console.log(node)
      this.$emit('addnode', node)
    },
    delNode() {
      this.$emit('delNode')
    }
  }
}
</script>
