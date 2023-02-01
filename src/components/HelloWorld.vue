<template>
  <head>
  </head>
  <body>
    <div class="card" style="margin-top:20px;">
      <div class="card-title" style="margin-bottom:10px;">
        Report Finding
      </div>
      <div class="card-body">
        <form>
          <div class="row">
            <div class="cell">
              <label>Type:</label>
            </div>
            <div class="cell" style="margin-top: 10px; margin-bottom: 20px;">
              <select required v-model="sighting" name="sighting-names" id="sighting-names">
                <option value="Moon">Moon</option>
                <option value="Planet">Planet</option>
                <option value="Galaxy">Galaxy</option>
                <option value="Star Cluster">Star Cluster</option>
                <option value="Binary Star">Binary Star</option>
                <option value="Nebulae">Nebulae</option>
                <option value="Comet">Comet</option>
                <option value="Man Made Object">Man-made object</option>
              </select>
            </div>
          </div>
          <div class="row">
            <div class="cell" style="margin-bottom: 10px;">
              <label>Additional Notes:</label>
            </div>
            <div class="cell">
              <div>
                  <input v-model="notes">
              </div>
            </div>
          </div>
          <div class="card-footer">
            <button type="button" class="btn" @click="handleSubmit" style="margin-top: 20px;">Submit</button>
          </div>
        </form>
      </div>
    </div>
    <br>
    <div class="underReport"><p>Sighting: {{ sighting }}</p></div>
    <br>
    <div class="underReport"><p>Notes:<br> {{ notes }}</p></div>
    <br>
    <div class="underReport">
      <strong>Findings Table</strong><br><br>
      <div style="border: 1px solid red">
        <li><br>
          Sighting &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Notes
        </li><br><br>
        <li
        v-for="item in list" :key="item.sighting">
        {{ item.sighting }} - {{ item.notes }} <br><br>
        </li>
      </div>
    </div>
  </body>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      notes: '',
      sighting: '',
      messageArray: [],
      list: [{ sighting: 'Example', notes: 'Example' }]
    }
  },
  methods: {
    handleSubmit () {
      console.log('form submitted')
      this.list.push({ sighting: this.sighting, notes: this.notes })
      console.log(this.sighting)
      console.log(this.notes)
    }
  },
  beforeMount () {
    this.list.shift()
  }
})

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
