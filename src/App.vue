<template>
  <div>
    <h2>親コンポーネント</h2>
    <input type="text" v-model="parentData">
    <the-child 
    :dataFromParent="parentData"
    @child-event="receiveDataFromChild"
    ></the-child>
  </div>
</template>

<!-- Option API -->
<!-- <script>
import TheChild from './components/TheChild.vue';

export default {
  components: {
    TheChild,
  },
  data() {
    return {
      parentData:'',
    };
  },
  methods: {
    receiveDataFromChild(dataFromChild) {
      this.parentData = dataFromChild;
    },
  },
}
</script> -->
<!-- Composition API NEW -->
<script setup>
import { ref } from 'vue';
import TheChild from './components/TheChild.vue';

const parentData = ref('');

const receiveDataFromChild = (dataFromChild) => {
  parentData.value = dataFromChild;
};
</script>