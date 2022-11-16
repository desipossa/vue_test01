<template>
  <div class="about">
    <h1 @click="tg" class="initial" :class="{ active: st }">
      This is an about page {{ num }}
    </h1>
    <button @click="setNum">더하기</button>
  </div>
</template>
  <script>
import { ref } from "vue";
export default {
  setup() {
    const num = ref(0);
    const setNum = () => {
      num.value++;
    };

    const st = ref(false);
    const tg = () => {
      st.value = !st.value;
    };
    return {
      num,
      setNum,
      st,
      tg,
    };
  },
};
</script>
  <style lang="scss" scoped>
.about {
  .active {
    color: red;
  }
}
</style>
  