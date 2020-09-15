<template>
  <table>
    <thead>
      <th>Sale End</th>
      <th>Maturity in</th>
      <th>Max accepts</th>
      <th>Already accepted</th>
      <th>Discount</th>
      <th>APY</th>
      <th class="see-bond" v-if="bond === undefined"></th>
    </thead>
    <tbody>
      <tr v-for="b in bondsList" :key="b.id">
        <td>{{ b.saleEnd }}</td>
        <td>{{ b.maturity }}</td>
        <td>{{ b.accepting }} {{ b.token }}</td>
        <td>{{ b.accepted }} {{ b.token }}</td>
        <td>{{ b.discount }}</td>
        <td>{{ b.apy }}</td>
        <td class="see-bond" v-if="bond === undefined">
          <router-link :to="{name: 'Bond', params: {address, bondId: b.id}}">
            See Bond
          </router-link>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import { computed } from 'vue'

export default {
  name: 'BondsTable',
  props: {
    address: String,
    bond: Object,
    bonds: Object
  },
  setup (props) {
    const bondsList = computed(() => props.bonds || [props.bond])
    return {
      bondsList
    }
  }
}
</script>

<style scoped>
table {
  width: 100%;
}
th {
  font-style: normal;
  font-weight: normal;
  padding-bottom: 20px;
  text-align: left;
  padding-right: 10px;
}

th:last-child {
  padding-left: 0px;
}

thead {
  margin-bottom: 10px;
}

td {
  color: #000;
  padding-bottom: 10px;
}

.see-bond {
  text-transform: uppercase;
}

</style>
