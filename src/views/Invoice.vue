<template>
  <h1>Invoice</h1>
  <table>
    <thead>
        <td>Name</td>
        <td>Unit</td>
        <td>Count</td>
        <td>Price</td>
        <td>Sum</td>
    </thead>
    <tbody>
      <ServiceList :serviceList="rows"/>
      <AddRow @add-row="addRow"/>
      
    </tbody>
  </table>
</template>

<script>
import { ref, computed } from "vue";
import ServiceList from "@/components/invoice/ServiceList.vue";
import AddRow from "@/components/invoice/edit/AddRow.vue";
export default {
  components: {
    ServiceList,
    AddRow
  },
  setup() {
    const rows = ref([["sai","tk","2","1.50","3"], 
      ["kohupiim","tk","4","0.99","3.95"]]); // name,unit,count,price,sum
    
    // const insertedRows = computed(function() {
    //   return rows;
    // });

    function addRow(data) {
      rows.value.push(data);
    }
    
    return {
      rows,
      addRow
    };
  }
};
</script>

<style>

</style>