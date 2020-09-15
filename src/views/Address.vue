<template>
  <BondIssuer :address="address" />
  <section class="card">
    <BondsTable :address="address" :bonds="bonds" />
  </section>
</template>

<script>
// @ is an alias to /src
import BondsTable from '@/components/BondsTable.vue'
import BondIssuer from '@/components/BondIssuer.vue'

export default {
  name: 'Address',
  props: ['address'],
  components: {
    BondsTable,
    BondIssuer
  },
  setup (props) {
    const saleEnd = '7 days'
    const maturity = '40 days'
    const accepted = 1000
    const accepting = 1000
    const token = 'LINK'
    const discount = '10%'
    const apy = '10%'

    const obj1 = {
      id: 0,
      saleEnd,
      maturity,
      accepted,
      accepting,
      token,
      discount,
      apy
    }

    const obj2 = {
      id: 1,
      saleEnd,
      maturity,
      accepted,
      accepting,
      token,
      discount,
      apy
    }

    return {
      bonds: [obj1, obj2]
    }
  }
}
</script>

<style scoped>
.disclaimer {
  margin-top: 20px;
  font-size: 0.9em;
}
.disclaimer span {
  text-transform: uppercase;
  font-weight: bold;
  line-height: 2.5em;
}
</style>
