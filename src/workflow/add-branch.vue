<template>
  <button
    class="add-branch"
    @click="addCondition"
  >
    添加条件
  </button>
</template>
<script>
export default {
  name: 'AddBranch',
  emits:['addCondition'],
  methods: {
    addCondition () {
      this.$emit('addCondition')
    }
  }
}
</script>
