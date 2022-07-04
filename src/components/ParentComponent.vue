<template>
  <div>
    <!-- try to get both events -->
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
      // works fine here
      console.log(`received from child: ${event.target.value}`);
    },
    gotWord() {
      // no event
      console.log(`received from child: ${event.target.value}`);
    }
  }
};
</script>
<style></style>
