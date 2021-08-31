<template>
  <el-popover
		v-bind= $attrs
		v-on= $listeners
    >
		<slot name="content"></slot>
		<template slot="reference">
			<slot name="renference"></slot>
		</template>
  </el-popover>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  created() {
    console.log(this.$attrs, this.$listeners)
  }
}
</script>
