<template>
  <div class="form">
    <div class="input">
      <label for="send">You send</label>
      <div class="input-box">
        <input id="send" type="text" name="send" :value="send">
        <span class="token">{{bond.token}}</span>
      </div>
    </div>

    <div class="input">
      <label for="receive">You receive</label>
      <div class="input-box">
        <input id="receive" type="text" name="receive" :value="receive">
        <span class="token">{{bond.token}}</span>
      </div>
    </div>

    <button type="submit" name="submit">
      Buy {{bond.token}} bond
    </button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'BondBuyer',
  props: {
    address: String,
    bond: Object
  },
  setup () {
    const send = ref(0)
    const receive = ref(0)

    return {
      send,
      receive
    }
  }
}
</script>

<style scoped>
.form {
  display: flex;
  border-top: 1px solid #F4F4F4;
  margin-top: 10px;
  padding-top: 40px;
}
label {
  display: block;
  color: #000;
  margin-bottom: 10px;
}
input, button {
  border-radius: 3px;
  border: none;
  font-size: 1em;
  font-family: "Roboto Mono", monospace;
}
input {
  background: #F4F4F4;
  padding: 13px 20px;
  width: 100%;
}
.input {
  margin-right: 70px;
}

.input-box {
  position: relative;
}

button {
  background: #223C59;
  color: #fff;
  text-transform: uppercase;
  height: 40px;
  text-align: center;
  margin-top: 31px;
  width: 180px;
}

.token {
  position: absolute;
  right: 10px;
  top: 12px;
}
</style>
