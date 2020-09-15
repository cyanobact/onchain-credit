<template>
  <BondIssuer :address="address" />
  <section class="card">
    <BondsTable :address="address" :bond="bond" />
    <BondBuyer :address="address" :bond=bond />
    <div class="disclaimer">
      <span>Disclaimer:</span>
      Buying bonds is highly risky!
      The bonds are not collateralized in any way.
      The issuer may choose not to repay the borrowed amount.
      You may lose all your funds!
    </div>
  </section>
</template>

<script>
// @ is an alias to /src
import BondsTable from '@/components/BondsTable.vue'
import BondBuyer from '@/components/BondBuyer.vue'
import BondIssuer from '@/components/BondIssuer.vue'

export default {
  name: 'Address',
  props: ['address', 'bondId'],
  components: {
    BondsTable,
    BondBuyer,
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

    const bond = {
      id: 0,
      saleEnd,
      maturity,
      accepted,
      accepting,
      token,
      discount,
      apy
    }

    // TODO
    return {
      bond
    }
  }
}
</script>

<style scoped>
.disclaimer {
  margin-top: 30px;
  font-size: 0.9em;
}
.disclaimer span {
  text-transform: uppercase;
  font-weight: bold;
  line-height: 2.5em;
}
</style>
