<template>
  <div>
    <ChildComponent @got-word="gotWord" @button-clicked="buttonClicked" />
  </div>
</template>
<script>
import ChildComponent from './ChildComponent.vue';
export default {
  name: 'ParentComponent',
  components: { ChildComponent },
  data() {
    return {};
  },
  methods: {
    buttonClicked() {
      console.log(`received from child: ${event.target.value}`);
    },
    gotWord() {
      console.log(`received from child: ${event.target.value}`);
    }
  }
};
</script>
<style></style>
