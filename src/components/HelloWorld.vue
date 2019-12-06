<template>
  <div class="hello">
    <h5>No Reactive</h5>
    <div v-for="(t, key) in noReactive" :key="key">
      <span>{{ key }}: {{ t }}</span>
    </div>
    <button @click="addElementNoReactive">Add without reactivity</button>

    <hr>

    <h5>Reactive</h5>
    <div v-for="(t, key) in reactive" :key="key">
      <span>{{key}}: {{ t }}</span>
    </div>
    <button @click="addElementReactive">Add with reactivity</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      noReactive: {
        first: "test 1"
      },
      reactive: {
        first: "el 1"
      }
    };
  },
  methods: {
    addElementNoReactive() {
      this.noReactive.second = "added no reactive ";

      console.log(this.noReactive);
    },
    addElementReactive() {
      this.$set(this.reactive, "second", "added reactive  element");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
