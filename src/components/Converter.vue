<template>
  <div>
  <h1>Kaalu teisendamine</h1>
  <h4>Sisesta kaal kilogrammides</h4>
  <input type="number" min="0" v-model="kg" oninput="this.value = this.value.slice(0,12)">
   <table v-if="kg !== ''">
       <tr>
           <td>Grammid</td>
           <td>{{ convertKg(1000) + ' g' }}</td>
       </tr>
       <tr>
           <td>Naelad</td>
           <td>{{ convertKg(2.20462) + ' lb' }}</td>
       </tr>
       <tr>
           <td>Untsid</td>
           <td>{{ convertKg(35.274) + ' oz' }}</td>
       </tr>
   </table>
  </div>
</template>

<script>
export default {
  name: 'Converter',
  data () {
    return {
      kg: ''
    }
  },
  methods: {
    convertKg (multiplier) {
      return (this.kg !== 0) ? (this.kg * multiplier).toFixed(2) : 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    td {
        padding-right: 10px;
    }
    div {
        text-align: center;
    }
    table {
        margin: 0 auto;
        text-align: left;
    }
    input {
        margin-bottom: 20px;
    }
</style>
