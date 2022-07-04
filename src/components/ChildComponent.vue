<template>
  <div>
    <header>Child Component</header>
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
      this.$emit('buttonClicked', 'you clicked the button');
    },
    childFunction() {
      let wordRange = ['hi', 'this', 'is', 'a', 'message'];
      for (let word of wordRange) {
        // console.log(word);
        this.$emit('gotWord', word);
      }
    }
  }
};
</script>
<style></style>
