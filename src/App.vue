<!-- <template> -->
  <!-- <div>
    <h2>親コンポーネント</h2>
    <input type="text" v-model="parentData">
    <the-child
    :dataFromParent="parentData"
    @child-event="receiveDataFromChild"
    ></the-child>
  </div> -->
<!-- </template> -->

<template>
  <div>
    <h2>親コンポーネント</h2>
    <input v-model="parentData" type="text">
    <the-child 
    :dataFromParent="parentData"
    @child-event="receiveDataFromChild"
    ></the-child>
  </div>
</template>

<script>
import TheChild from './components/TheChild.vue';

export default {
  components: {
    TheChild,
  },
  data() {
    return {
      parentData: '',
    };
  },
  methods: {
    receiveDataFromChild(dataFromChild) {
      this.parentData = dataFromChild;
    },
  },
}
</script>

<!-- Option API -->
<!-- <script>
import TheChild from './components/TheChild.vue';

export default {
  components: {
    TheChild,
  },
  data() {
    return {
      parentData: '',
    };
  },
  methods: {
    receiveDataFromChild(DataFromChild) {
      this.parentData = DataFromChild;
    },
  },
} -->
<!-- </script> -->

<!-- Composition API NEW -->