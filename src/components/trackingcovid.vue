<template>
<div>
  <input type="text" placeholder="country" v-model="country">
  <input type="date" class="form-control" v-model="start">
 
<input type="date" class="form-control" v-model="end">
 
<button @click="submit">submit</button>
<div class="liItems">
  <ul>
    <li v-for="country in result" :key="country"> <div>Date: {{country.Date}}</div> <div>Confirmed Cases: {{country.Confirmed}}</div> 
     <div>Active Cases: {{country.Active}}</div>  <div> Deaths: {{country.Deaths}} </div> </li>
    
  </ul>
  
</div>

</div>
  
</template>

<script>
import axios from 'axios';
export default {
  name: 'trackingcovid',
  data(){
    return{
      country:'',
      start:'',
      end:'',
      result:"",
      resultCoultry:[],
      resultDate:[]
    }
  },
  methods:{
    submit(){
      let remove = this.country.split(" ").join("%20");
      axios
      .get(`https://api.covid19api.com/country/${remove}?from=${this.start}T00:00:00Z&to=${this.end}T00:00:00Z`)
      .then(res => {
        this.result = res.data

      })
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}


li {
    width: 100%;
   
    padding: 20px;
    height: 100px;
    
}
li[data-v-9a480624] {
  
    background: #EAB67C;
    margin: 20px;
    width: 400px;
    border-radius: 5px;
    color: white;
}
.liItems{
  display: flex;
  justify-content: center;
}
div {
    padding: 4px;
}
input {
    padding: 10px;
    text-align: center;
    margin: 0px 20px;
    border:none;
    width: 200px;
   
}
button {
    border: none;
    padding: 10px;
    width: 200px;
    font-size: 15px;
    background:  #EAB67C;
}


</style>
