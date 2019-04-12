<template>
    <table :class="className">
        <thead>
            <tr>
                <th :key="column.id" v-for="column in columns">
                    {{ column.label }}
                </th>
                <th v-if="haveActions"></th>
            </tr>
        </thead>
        <tbody>
            <tr :key="row.id" v-for="row in rows">
              <td :key="column.id + row.id" v-for="column in columns">
                <template v-if="!column.component">{{ row[column.name] }}</template>
                <component v-else-if="column.component" :is="column.component" :format="format" :row="row" />
              </td>
              <td v-if="haveActions">
                <slot name="actions" :row="row" />
              </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    name: 'MblDataTable',
    props: {
        className: String,
        columns: Array,
        rows: Array,
        haveActions: Boolean
    },
}
</script>

<style lang="scss" scoped>

</style>