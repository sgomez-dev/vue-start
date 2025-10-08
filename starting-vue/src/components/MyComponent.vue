<template>
  <div class="my-component">
    <h1 v-if="isVisible">{{ title }}</h1>
    <h2 v-bind:class="{ highlighted: isHighlighted }">{{ name }}</h2>
    <p>This is a simple Vue component.</p>
    <button @click="toggleVisibility">
      {{ isVisible ? "Hide" : "Show" }} Title
    </button>
  </div>
  <hr />
  <input type="text" v-model="title" placeholder="Type something..." />
  <button @click="sayHello">Make alert</button>
  <hr />
  <button @click="toggleHighlight">
    {{ isHighlighted ? "Remove Highlight" : "Highlight Name" }}
  </button>
  <hr />
  <ul>
    <li v-for="item in list" :key="item.id">{{ item.name }}</li>
  </ul>

  <div id="app">
    <h1>{{ storeTitle }}</h1>
  </div>
</template>

<script>
import { mapState, mapMutations } from "vuex";

export default {
  name: "MyComponent",
  data() {
    return {
      title: "Hello, Vue!",
      name: "Santiago",
      isHighlighted: false,
      isVisible: true,
      list: [
        { id: 1, name: "Item 1" },
        { id: 2, name: "Item 2" },
        { id: 3, name: "Item 3" },
      ],
    };
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    },
    sayHello() {
      alert(this.title);
    },
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted;
    },
  },
};
</script>

<style scoped>
.highlighted {
  color: #48e369;
  font-weight: bold;
}
</style>
