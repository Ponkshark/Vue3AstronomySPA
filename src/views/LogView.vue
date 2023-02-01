<template>
    <div class="log">
        <h1>Log</h1>
    </div>
    <!-- <div v-for="data in logData" :key="data" class="logdata">
        <span @click="deleteLog(data)">{{ data }}</span>
    </div> -->
    <div id="data-cont">
    <p>Name: {{ logData.name }}, Diameter: {{ logData.diameter }}, Reference: {{ logData.id }}<br> First Observation: {{ logData.first_obs }}, Last Observation: {{ logData.last_obs }}, Total Observations: {{ logData.n_obs_used }}</p><br><br>
    <p>Name: {{ logData2.name }}, Diameter: {{ logData2.diameter }}, Reference: {{ logData2.id }}<br> First Observation: {{ logData2.first_obs }}, Last Observation: {{ logData2.last_obs }}, Total Observations: {{ logData2.n_obs_used }}</p><br><br>
    <p>Name: {{ logData3.name }}, Diameter: {{ logData3.diameter }}, Reference: {{ logData3.id }}<br> First Observation: {{ logData3.first_obs }}, Last Observation: {{ logData3.last_obs }}, Total Observations: {{ logData3.n_obs_used }}</p><br><br>
    <p>Name: {{ logData4.name }}, Diameter: {{ logData4.diameter }}, Reference: {{ logData4.id }}<br> First Observation: {{ logData4.first_obs }}, Last Observation: {{ logData4.last_obs }}, Total Observations: {{ logData4.n_obs_used }}</p><br><br>
  </div><br><br>
      <strong> Known asteroid diameter checker </strong><br><br>
      <input
      v-model="logtext"
      >
      <button  class="btn" @click="fetchUserInput" style="margin-left: 10px;">
        Submit
      </button><br><br>
      <p>Name: {{ logData5.name }}, Diameter: {{ logData5.diameter }}</p>

</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  data () {
    return {
      logData: [],
      logData2: [],
      logData3: [],
      logData4: [],
      logData5: [],
      logtext: '',
      errormessage: ''
    }
  },
  mounted () {
    fetch('http://www.asterank.com/api/asterank?query= { "name" : "Pallas" } &limit=1')
      .then(res => res.json())
      .then(data => {
        const set = new Set(data)
        for (const item of set) {
          console.log(item)
          this.logData = item
        }
      })
      .catch(err => console.log(err.message))
    fetch('http://www.asterank.com/api/asterank?query= { "name" : "Ornamenta" } &limit=1')
      .then(res => res.json())
      .then(data => {
        const set = new Set(data)
        for (const item of set) {
          console.log(item)
          this.logData2 = item
        }
      })
      .catch(err => console.log(err.message))
    fetch('http://www.asterank.com/api/asterank?query= { "name" : "Deborah" } &limit=1')
      .then(res => res.json())
      .then(data => {
        const set = new Set(data)
        for (const item of set) {
          console.log(item)
          this.logData3 = item
        }
      })
      .catch(err => console.log(err.message))
    fetch('http://www.asterank.com/api/asterank?query= { "name" : "Seeligeria" } &limit=1')
      .then(res => res.json())
      .then(data => {
        const set = new Set(data)
        for (const item of set) {
          console.log(item)
          this.logData4 = item
        }
      })
      .catch(err => console.log(err.message))
  },
  methods: {
    // test 1, using inputted data
    // deleteLog (data:string) {
    //   this.logData = this.logData.filter((item:string) => {
    //     return data !== item
    //   })
    // }
    fetchUserInput () {
      fetch('http://www.asterank.com/api/asterank?query= { "name" : "' + this.logtext + '" } &limit=1')
        .then(res => res.json())
        .then(data => {
          const set = new Set(data)
          for (const item of set) {
            console.log(item)
            this.logData5 = item
          }
        })
        .catch(err => console.log(err.message))
    }
  }
})

</script>
