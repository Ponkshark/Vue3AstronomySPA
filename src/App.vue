<template>
  <app-header />
  <router-view/>
  <app-footer />
</template>

<script lang="ts">
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppHeader,
    AppFooter
  }
}

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}
body {
  background-color: #330033;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400' viewBox='0 0 800 800'%3E%3Cg fill='none' stroke='%23404' stroke-width='1'%3E%3Cpath d='M769 229L1037 260.9M927 880L731 737 520 660 309 538 40 599 295 764 126.5 879.5 40 599-197 493 102 382-31 229 126.5 79.5-69-63'/%3E%3Cpath d='M-31 229L237 261 390 382 603 493 308.5 537.5 101.5 381.5M370 905L295 764'/%3E%3Cpath d='M520 660L578 842 731 737 840 599 603 493 520 660 295 764 309 538 390 382 539 269 769 229 577.5 41.5 370 105 295 -36 126.5 79.5 237 261 102 382 40 599 -69 737 127 880'/%3E%3Cpath d='M520-140L578.5 42.5 731-63M603 493L539 269 237 261 370 105M902 382L539 269M390 382L102 382'/%3E%3Cpath d='M-222 42L126.5 79.5 370 105 539 269 577.5 41.5 927 80 769 229 902 382 603 493 731 737M295-36L577.5 41.5M578 842L295 764M40-201L127 80M102 382L-261 269'/%3E%3C/g%3E%3Cg fill='%23505'%3E%3Ccircle cx='769' cy='229' r='5'/%3E%3Ccircle cx='539' cy='269' r='5'/%3E%3Ccircle cx='603' cy='493' r='5'/%3E%3Ccircle cx='731' cy='737' r='5'/%3E%3Ccircle cx='520' cy='660' r='5'/%3E%3Ccircle cx='309' cy='538' r='5'/%3E%3Ccircle cx='295' cy='764' r='5'/%3E%3Ccircle cx='40' cy='599' r='5'/%3E%3Ccircle cx='102' cy='382' r='5'/%3E%3Ccircle cx='127' cy='80' r='5'/%3E%3Ccircle cx='370' cy='105' r='5'/%3E%3Ccircle cx='578' cy='42' r='5'/%3E%3Ccircle cx='237' cy='261' r='5'/%3E%3Ccircle cx='390' cy='382' r='5'/%3E%3C/g%3E%3C/svg%3E");
  margin: 0px;
}
p {
  margin: 0px;
}
header {
  margin-top: 10px;
}
footer {
  position: static;
  margin: auto;
  margin-top: 10vh;
  height: 20px;
  bottom: 10px;
  left: 50%;
  clear:both;
  p {
    background-color: #330033;
  }
}
.navlinks {
  margin-right: 10px;
  margin-left: 10px;
  background-color: #1a535c;
  border-radius: 5px;
  padding: 5px;

  a {
    color: #c0c0c0;
    text-decoration: none;
  }
}
.navlinks:hover {
  background-color: #15434a;
}
.navlinks .active-link {
  color: white;
}
.card{
  width: 230px;
  padding: 10px;
  padding-bottom: 20px;
  margin: auto;

  border-bottom: 1px solid #c42021;
}
#sighting-names {
  padding: 5px;
}
.logdata {
  width: 50vw;
  margin: auto;
  margin-bottom: 50px;
}
.logdata:hover {
  cursor: pointer;
  color: #c42021;
}
.btn {
  border-radius: 5px;
  padding: 5px;
  color: white;
  background-color:#1a535c;
  border: none;
  &:hover{
    cursor: pointer;
    background-color: #15434a;
  }
}
.underReport {
  width: 230px;
  margin: auto;
  p {
    width: 230px;
  }
}
</style>
