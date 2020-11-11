<template>
  <tr>
    <td><input type="text" name="name"  v-model="name"></td>
    <td><input type="text" name="unit"  v-model="unit"></td>
    <td><input type="text" name="count"  v-model="count"></td>
    <td><input type="text" name="price"  v-model="price"></td>
    <td><input type="text" name="sum"  v-model="sum"></td>
    <td><button @click="add()">Add</button></td>
  </tr>
</template>

<script>
import { ref, computed } from "vue";
export default {
  emits: ["add-row"],
  setup(_, context) {
    const name = ref("muna");
    const unit = ref("tk") ;
    const count = ref("1");
    const price = ref("0.99");
    const sum = ref("0.99");

    const invalidInput = ref(false);
    
    const newRow = computed(function() {
      return [name.value, unit.value, count.value,
        price.value, sum.value];
    });

    function add() {
      if (name.value === "" || unit.value === "" || count.value === "" || 
        price.value === "" || sum.value === "") {
        invalidInput.value = false;
        return;
      }
      context.emit("add-row", newRow.value);

    }
    return {
      name,
      unit,
      count,
      price,
      sum,
      add
    };

  }
};
</script>

<style>

</style>