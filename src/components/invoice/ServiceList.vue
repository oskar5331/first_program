<template>
      <tr v-for="(row, key) in serviceList" :key="key">
        <td>{{ row[0] }}</td>
        <td>{{ row[1] }}</td>
        <td>{{ row[2] }}</td>
        <td>{{ row[3] }}</td>
        <td>{{ row[4] }}</td>
      </tr>
</template>

<script>
import { ref, computed, toRef } from "vue";
export default {
  props: {
    serviceList: Array
  }
  // emits: ["remove-row"],
  // setup(props) {
  //   const { serviceList } = toRef(props);

  // }

};
</script>

<style>

</style>