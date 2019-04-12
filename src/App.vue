<template>
  <div id="app">
    <MblDataTable :columns="testColumns" :rows="testRows"  />
  </div>
</template>

<script>
import MblDataTable from '@/components/MblDataTable'
export default {
  name: 'app',
  components: {
    MblDataTable
  },
  data() {
    return {
      testColumns: [
        {
          id: 1,
          label: 'ID',
          name: 'id',
        },
        {
          id: 2,
          label: 'Age',
          name: 'age',
        },
      ],

      testRows: [
        {
          id: 111,
          age: 33,
        },
        {
          id: 222,
          age: 77,
        },
      ],

    }
  },
}
</script>

