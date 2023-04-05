<template>
  <div class="container">
    <Header title="Torre" />
    <GetUser @get-skills="fetchSKills"/>
    <Skills :skills="skills"/>
  </div>
</template>

<script>
import Header from "./components/Header"
import Skills from "./components/Skills"
import GetUser from "./components/GetUser"
import axios from "axios"


export default {
  name: 'App',
  components: {
    Header,
    Skills,
    GetUser,
  },

  methods:{
    async fetchSKills(id){
      
      const res = await axios.get(`http://localhost:8080/user/iyadmfh50`);   
      this.skills = res.data.strengths
    }
  },

  data(){
    return{
      skills:[],
    }
  },
  created(){
    this.skills =[]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}</style>
