<template>
    <div class="log">
        <h1>Log</h1>
    </div>
    <!-- <div v-for="data in logData" :key="data" class="logdata">
        <span @click="deleteLog(data)">{{ data }}</span>
    </div> -->
    <p>{{ logData }}</p>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

export default defineComponent({
  data () {
    return {
      logData: []
    }
    // test 1, using inputted data
    // return {
    //   logData: ['Object name: STF156, Identifier: WDS01485+6027, Object type: Double star, Constellation: Cassiopeia, R.A/Dec. -J2000.0: 01:48:29 +60°26`32", Telescope - eyepiece: 14" LX850 SCT - LX850 - 16mm Nagler T5, Mag./FoV: 178x/28`', 'Object name: NGC663 - "Letter S Cluster", Identifier: NGC663, Object type: Open cluster, Constellation: Cassiopeia, R.A/Dec. -J2000.0: 01:46:09 +61°14`06", Telescope - eyepiece: 14" LX850 SCT - LX850 - 16mm Nagler T5, Mag./FoV: 178x/28`', 'Object name: 33 Pegasi, Identifier: WDS22237+2051, Object type: Double star, Constellation: Pegasus, R.A/Dec. -J2000.0: 22:23:40 +20°50`54", Telescope - eyepiece: 14" LX850 SCT - LX850 - 16mm Nagler T5, Mag./FoV: 178x/28`']
    // }
  },
  mounted () {
    fetch('http://www.asterank.com/api/asterank?query= { "name" : "Pallas" } &limit=1')
      .then(res => res.json())
      .then(data => this.logData === data)
      .catch(err => console.log(err.message))
  },
  methods: {
    // test 1, using inputted data
    // deleteLog (data:string) {
    //   this.logData = this.logData.filter((item:string) => {
    //     return data !== item
    //   })
    // }
  }
})

</script>
