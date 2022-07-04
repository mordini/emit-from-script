<template>
  <div>
    <header>Child Component</header>
    <!-- user interaction generates event -->
    <button @click="clickedButton" value="a toy">click me</button>
  </div>
</template>
<script>
export default {
  emits: ['gotWord', 'buttonClicked'],
  name: 'ChildComponent',
  components: {},
  data() {
    return {};
  },
  mounted() {
    this.childFunction();
  },
  methods: {
    clickedButton() {
      // works just fine because there's user input triggering event?
      this.$emit('buttonClicked', 'you clicked the button');
    },
    childFunction() {
      let wordRange = ['hi', 'this', 'is', 'a', 'message'];
      for (let word of wordRange) {
        // I'd like to send a signal to the parent to run
        // a function from within
        // but I suspect because there's no real event, this breaks
        this.$emit('gotWord', word);
      }
    }
  }
};
</script>
<style></style>
