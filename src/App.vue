<template>
<!--
  Part I
<AirportCards />
<airport-cards />當引用組件時，Vue不在乎使用哪個組件。所有大寫的單詞和字母將由連字符分隔，並且將小寫。
<airport-cards />同等<airport-cards />寫法
-->
<p>Part II</p>
<AirportCards :airports="usAirports" />
<airport-cards :airports="euAirports" />
<card>
    <p>US Airports</p>
    <p>Total: {{ usAirports.length }}</p>
  </card>
  <card>
    <p>EU Airports</p>
    <p>Total: {{ euAirports.length }}</p>
  </card>
</template>

<script>
import { ref } from 'vue'
import AirportCards from '@/components/AirportCards.vue' //Part I
import usAirportData from '@/data/us-airports.js'
import euAirportData from '@/data/eu-airports.js'
import Card from '@/components/Card.vue'

export default {
  name: 'App',
  components: { //Part I
    AirportCards,
    Card
  },
  setup() { //Part II
    const usAirports = ref(usAirportData)
    const euAirports = ref(euAirportData)
    return { usAirports,euAirports }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>