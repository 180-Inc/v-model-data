<template>
  <div>
    <h2>子コンポーネント</h2>
    <p>親から受け取ったデータですよ：{{ dataFromParent }}</p>
    <button @click="sendDataToParent">子のデータを親に送る</button>
  </div>
</template>

<!-- <script>
export default {
  props: ['dataFromParent'],
  emits:['child-event'],
  data() {
    return {
      childData: '子が持っているデータですよ',
    };
  },
  methods: {
    sendDataToParent() {
      this.$emit('child-event', this.childData);
    },
  },
}
</script> -->

<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps(['dataFromParent']);
const emits = defineEmits(['child-event']);

const childData = ref('子が持っているデータですよ');

const sendDataToParent = () => {
  emits('child-event', childData.value);
};

</script>

<!-- Composition API NEW -->
<!-- <script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps(['dataFromParent']);
const emits = defineEmits(['child-event']);

const childData = ref('子が持つデータ');

const sendDataToParent = () => {
  emits('child-event', childData.value);
};

</script> -->

