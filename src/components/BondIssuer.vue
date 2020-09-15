<template>
  <div class="bond-issuer">
    Bond issuer:
    <span>
      <router-link :to="{name: 'Address', params: { address: address }}">
        {{ address }}
      </router-link>
    </span>
  </div>
</template>

<script>
export default {
  name: 'BondIssuer',
  props: ['address']
}
</script>

<style scoped>
.bond-issuer {
  margin-top: 40px;
  margin-bottom: 30px;
}
.bond-issuer span {
  color: #000;
}
.bond-issuer a {
  text-decoration: none;
}
</style>
