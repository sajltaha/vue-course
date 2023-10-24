<script>
import axios from "axios";
export default {
  data: () => {
    return {
      info: null,
      EURInfo: null,
      USDInfo: null,
      GBPInfo: null,
    };
  },
  watch: {
    info() {
      this.EURInfo = this.info.EUR;
      this.USDInfo = this.info.USD;
      this.GBPInfo = this.info.GBP;
      console.log(this.EURInfo);
    },
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then((response) => response.data)
      .then((res) => {
        this.info = res.bpi;
        console.log(this.info);
      });
  },
};
</script>

<template>
  <div class="card">{{ info }}</div>
</template>

<style scoped></style>
