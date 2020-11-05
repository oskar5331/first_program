<template>
  <table>
    <thead>
        <td>Name</td>
        <td>Unit</td>
        <td>Count</td>
        <td>Price</td>
        <td>Sum</td>
    </thead>
    <tbody>
      <tr v-for="(row, key) in rows" :key="key">
        <td>{{ row[0] }}</td>
        <td>{{ row[1] }}</td>
        <td>{{ row[2] }}</td>
        <td>{{ row[3] }}</td>
        <td>{{ row[4] }}</td>
      </tr>
      <tr>
        <td><input type="text" name="name"  v-model="name"></td>
        <td><input type="text" name="name"  v-model="unit"></td>
        <td><input type="text" name="name"  v-model="count"></td>
        <td><input type="text" name="name"  v-model="price"></td>
        <td><input type="text" name="name"  v-model="sum"></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import { ref, computed } from 'vue'
export default {
    setup() {
      const rows = ref([['sai'],['tk'],['2'],['1.50'],['3']]) // name,unit,count,price,sum
      const nameunit = ref('')
      const count = ref('')
      const price = ref('')
      const sum = ref('')

    }

}
</script>

<style>

</style>