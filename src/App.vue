<template>
  <div id="app">
    <p>-----------组件用法-----------</p>
    <p>选择想要的车型</p>
    <p>日系：</p>
    <Radio v-model="jpRadio" label="1" @input="carChange">途达</Radio>
    <Radio v-model="jpRadio" label="2" @input="carChange">奇骏</Radio>
    <Radio v-model="jpRadio" label="3" @input="carChange">RAV4</Radio>
    <p>最终选择日系车型的值：{{ jpRadio }}</p>

    <p>德系：</p>
    <Radio v-model="geRadio" label="1" @input="carChange">A4L</Radio>
    <Radio v-model="geRadio" label="2" @input="carChange">C200</Radio>
    <p>最终选择德系车型的值：{{ geRadio }}</p>



    <p style="padding:50px 0 0 0">-----------非组件用法-----------</p>
    <input type="radio" name="" id="qq" value="qq" v-model="normal" @click="normalCHange" />
    <label for="qq">qq</label>
    <input type="radio" name="" id="ww" value="ww" v-model="normal" @click="normalCHange" />
    <label for="ww">ww</label>
  </div>
</template>

<script>
import Radio from "./components/Radio";
export default {
  name: "App",
  components: {
    Radio,
  },
  data() {
    return {
      jpRadio: "1",
      geRadio: "2",
      normal: "ww",
    };
  },
  methods: {
    carChange(e) {
      console.log("当前选中的单选框的值", e, typeof e);
    },
    normalCHange(e) {
      console.log("normal", e.target.value);
    },
  },
};
</script>

<style>
#app {
}
</style>
