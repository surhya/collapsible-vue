<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <HelloWorld/> -->
        <TabComp :acctype="bank.acctype" :accnumber="bank.accnumber" :bname="bank.bname" :accname="bank.accname"/>
        

  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld'
import TabComp from './components/TabComp'

export default {
  name: 'App',
  components: {
   // HelloWorld,
    TabComp
  },
 data() {
   return {
      bank: {
        acctype: 'Current',
        accnumber : 5001010956478,
        bname : 'SBM Bank (Marutius) LTD',
        accname: 'LCV Trade Finance Fund'
      }
   }
 }

}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
