<template>
  <div class="home">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <popper class="popper" :title="title" trigger="hover" placement="bottom" :width="width" @show="showPop">
      <!-- 提示框显示内容 -->
      <template v-slot:content>
        <p>popper内容</p>
      </template>
      <!-- 触发部分 -->
      <template v-slot:renference>
        <el-button >插入内容</el-button>
      </template>
    </popper>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import popper from './popper.vue'
export default {
  name: 'Home',
  components: {
    // HelloWorld,
    popper
  },
  data(){
    return {
      title:'popper标题',
      width: '100'
    }
  },
  methods:{
    showPop(){
      console.log('show')
    }
  }
}
</script>
