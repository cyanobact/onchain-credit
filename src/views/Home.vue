<template>
  <div class="home">
    <h1>Welcome,</h1>
    <p>You can ask for a loan or providing liquidity to existing ones.</p>
    <p>This is part of <a href="https://letsbuild.finance">BUILD</a>.</p>
    <div class="card">
      <label for="address">
        Look for an address
      </label>
      <input type="text" placeholder="0x12345" :value="address">
      <button @click='search()' type="button" name="button">Search</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'Home',
  setup () {
    const address = ref('')
    const search = () => {
      window.location.href = address.value
    }
    return {
      address,
      search
    }
  }
}
</script>

<style scoped>
input {
  background: #F4F4F4;
  padding: 13px 20px;
}
input, button {
  border-radius: 3px;
  border: none;
  font-size: 1em;
  font-family: "Roboto Mono", monospace;
}
button {
  background: #223C59;
  color: #fff;
  text-transform: uppercase;
  height: 40px;
  text-align: center;
  width: 180px;
  margin-left: 30px;
}
</style>
