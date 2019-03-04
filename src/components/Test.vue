<template>
  <div class="example">
    <div class="tabs">
      <button class="tab" v-on:click="clickTab1">tab1</button>
      <button class="tab" v-on:click="clickTab2">tab2</button>
      <button class="tab" v-on:click="clickTab3">tab3</button>
    </div>
    <div class="contents">
      <component :is="currentComponent"></component>
    </div>
  </div>
</template>

<script>
import TestComponent1 from './TestComponent1.vue'
import TestComponent2 from './TestComponent2.vue'
import TestComponent3 from './TestComponent3.vue'

export default {
  components: {
    TestComponent1,
    TestComponent2,
    TestComponent3
  },
  data() {
    return {
      currentComponent: "TestComponent1"
    }
  },
  methods: {
    clickTab1() {
      this.currentComponent = "TestComponent1"
    },
    clickTab2() {
      this.currentComponent = "TestComponent2"
    },
    clickTab3() {
      this.currentComponent = "TestComponent3"
    }
  }
}
</script>

<style scoped>
.contents {
  position: relative;
  overflow: hidden;
  width: 800px;
  height: 800px;
  border: 2px solid rgb(88, 88, 88);
}
.tab {
  border-radius: 2px 2px 0 0;
  background: rgb(199, 199, 199);
  color: #311d0a;
  line-height: 24px;
}
.tab:hover {
  background: #eeeeee;
}
</style>