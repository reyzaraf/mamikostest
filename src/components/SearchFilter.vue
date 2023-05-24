<template>
    <div id="SearchFunction">
      <!-- Input Box for Search -->
      <h3>Search Field</h3>
      <input class="searchform" type="text" v-model="search" placeholder="enter a name here to filter..."> 
      <!-- Show List data listname -->
      <div class="lists" v-for="listname in filteredlistnames" :key="listname.id">
          <div :listname="listname">
            <h2>{{listname.name}}</h2>
          </div>
      </div>
      <!-- end of show list data listname -->
    </div>
  </template>
  
  <script>
  export default {
    name: 'SearchFilter',
    components: {
    },
    data() {
      return {
        search: "",
        listnames: [
          {
            id: 1,
            name: "Aditama"
          },
          {
            id: 2,
            name: "Giga"
          },
          {
            id: 3,
            name: "Reynaldy Zara"
          },
          {
            id: 4,
            name: "Jon Piring"
          },
        ]
      };
    },
    computed: {
      filteredlistnames() {
        // function to filter list names from array listnames
        return this.listnames.filter(listname => listname.name.toLowerCase().includes(this.search.toLowerCase()));
      }
    }
  };
  </script>
  
  <style>
  #SearchFunction {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    border: #2c3e50 2px solid;
    padding:5%;
  }
  .lists{
    background-color: #2c3e50;
    color: white;
  }
  .searchform{
    width: 400px;
    padding:10px;
    border-radius: 20px;
  }
  </style>
  