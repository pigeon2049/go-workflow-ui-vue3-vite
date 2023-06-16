<template>
  <div>
    <NodeWrap
        v-if="node.type === 'start' || node.type === 'approver' || node.type === 'notifier'"
        :node="node"
        @addnode="addnode"
        @delNode="delNode"
    />
    <ConditionNode
        v-if="node.type === 'condition'"
        :node.sync="node"
        @addnode="addnode"
        @delConditionNode="delConditionNode"
        @addConditionFactor="addConditionFactor"
    />
    <BranchWrap
        v-if="node.type === 'route'"
        :node="node"
        @addnode="addnode"
        @delNode="delNode"
    />
  </div>
</template>
<script>
import NodeWrap from './node-wrap.vue'
import ConditionNode from './condition-node.vue'
import BranchWrap from './branch-wrap.vue'
export default {
  name: 'Node',
  emits:['addnode','delNode','delConditionNode','addConditionFactor','update:node'],
  components: {
    NodeWrap,
    BranchWrap,
    ConditionNode
  },
  props: {
    node: {
      type: Object,
      default: undefined
    }
  },
  methods: {
    addnode (node) {
       console.log('node 新节点:')
       console.log(node)
      this.$emit('addnode', node)
    },
    delNode () {
      this.$emit('delNode')
    },
    delConditionNode () {
      this.$emit('delConditionNode')
    },
    addConditionFactor (node) {
      this.$emit('addConditionFactor', node)
      this.$emit('update:node', node)
      console.log(this.node)
    }
  }
}
</script>
