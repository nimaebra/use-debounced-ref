<template>
  <input v-model="query" type="text" />
</template>

<script>
import { watch } from "vue";
import useDebouncedRef from "./composables/useDebouncedRef";

export default {
  setup() {
    const query = useDebouncedRef("", 500);
    watch(query, (newQuery) => {
      console.log(newQuery);
      // call an API request or something else!
    });
    return { query };
  },
};
</script>
