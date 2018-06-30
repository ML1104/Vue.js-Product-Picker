<template>
  <div id="app">
    <Navigation></Navigation>
    <Editions @selectStandardEdition="setStandardEdition" @selectProEdition="setProEdition" @selectEnterpriseEdition="setEnterpriseEdition"></Editions>
    <Users @userCount="userCount = '1'" @addUser="incrementUsers" @removeUser="decrementUsers" :users="userCount"></Users>
    <Years @yearOne="setYearOne" @yearTwo="setYearTwo" @yearThree="setYearThree"></Years>
    <Support @standardSupport="setStandardSupport" @prioritySupport="setPrioritySupport"></Support>
    <Summary :edition="editionValue" :price="editionPrice" :durationPrice="yearPrice" :quantity="userCount" :duration="years" :support="supportType" :supportChoicePrice="supportTypePrice"></Summary>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Navigation from './components/Navigation.vue'
import Editions from './components/Editions.vue'
import Users from './components/Users.vue'
import Years from './components/Years.vue'
import Support from './components/Support.vue'
import Summary from './components/Summary.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Navigation,
    Editions,
    Users,
    Years,
    Support,
    Summary,
  },

  data: function() {
    return {
      editionValue: "",
      editionPrice: "",
      userCount: "",
      years: "",
      yearPrice: "",
      supportType: "",
      supportTypePrice: "",
      discounted: "",
      total: "",
    }
  },

  methods: {
    setStandardEdition() {
      this.editionValue = "Standard";
      this.editionPrice = 150;
    },

    setProEdition() {
      this.editionValue = "Pro";
      this.editionPrice = 300;
    },

    setEnterpriseEdition() {
      this.editionValue = "Enterprise";
      this.editionPrice = 600;
    },

    incrementUsers() {
      this.userCount++;
    },

    decrementUsers() {
      this.userCount--;
    },

    setYearOne() {
      this.years = "1 Year";
      this.yearPrice = "0"
    },

    setYearTwo() {
      this.years = "2 Years";
      this.yearPrice = "74"
    },

    setYearThree() {
      this.years = "3 Years";
      this.yearPrice = "149";
    },

    setStandardSupport() {
      this.supportType = "Standard";
    },

    setPrioritySupport() {
      this.supportType = "Priority";
      this.supportTypePrice = "149"
    },

    hasDiscount() {
      if (this.userCount >= "7") {
        this.discounted = "10% Multi-User Discount";
      } else {
        this.discounted = "Add Multi-User Discount";
      }
    },
  }
}
</script>

<style>

body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: 'Scada', sans-serif;
}
</style>
