<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <p>{{ text | toUppercase | toLowercase }}</p>
        <input v-model="filterText" />
        <ul>
          <li v-for="fruit in filteredFruits">{{ fruit }}</li>
        </ul>
      </div>
    </div>
    <app-list></app-list>
  </div>
</template>

<script>
import List from "./List.vue";
import { fruitMixin } from "./fruitMixin";

export default {
  data() {
    return {
      text: "Hello there!"
    };
  },
  mixins: [fruitMixin],
  filters: {
    toUppercase(value) {
      return value.toUpperCase();
    }
  },
  components: {
    "app-list": List
  }
};
</script>

<style>
</style>
