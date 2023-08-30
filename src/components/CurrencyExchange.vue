<template>
  <div>台幣: <input v-model="twd" type="number" v-on:blur="changeFromTw()"/></div>
  <div>
    美金: <input v-model="usd" type="number" v-on:blur="changeFromUs()"/>
  </div>
  <div>
    日幣: <input v-model="jpd" type="number" v-on:blur="changeFromJp()"/>
  </div>
</template>

<script>
export default {
  name: 'CurrencyExchange',
  data() {
    return {
      twd: 1,
      usd: 31.85,
      jpd: 0.22
    }
  },
  methods: {
    changeFromTw() {
      this.usd = (this.twd / 31.85).toFixed(1);
      this.jpd = (this.twd / 0.22).toFixed(1);
    },
    changeFromJp() {
      this.twd = (this.jpd * 0.22).toFixed(1);
      this.usd = (this.twd / 31.85).toFixed(1);
    },
    changeFromUs() {
      this.twd = (this.usd * 31.85).toFixed(1);
      this.jpd = (this.twd / 0.22).toFixed(1);
    }
  },
  computed: {
    // usd: {
    //   get() {
    //     return Number.parseFloat(Number(this.twd) / 31.85).toFixed(3);
    //   },
    //   set(value) {
    //     this.twd = Number.parseFloat(Number(value) * 31.85).toFixed(3);
    //   }
    // },
    // jpd: {
    //   get() {
    //     return Number.parseFloat(Number(this.twd) / 0.22).toFixed(3);
    //   },
    //   set(value) {
    //     this.twd = Number.parseFloat(Number(value) * 0.22).toFixed(3);
    //   }
    // }

  }
}
</script>
