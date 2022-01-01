<template>
  <div id="app">
      <main>
      <div class="search-box">
      <input 
      type="text" 
      class="search-bar" 
      placeholder="Search..."
       v-model="query"
       @keypress="fetchWeather"
      
      />
     {{ query }}
      </div>

      <div class="weather-wrap">
      <div class="location-box">
      <div class="location">California, US</div>
      <div class="date">Saturday 1 January 2022</div>
      </div>

      <div class="weather-box"> 
      <div class="temp">10ºC</div>
      <div class="weather">Rain</div>
      </div>
      </div>
      </main>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      api_key: 'dbbedde9ee53a9bcac9ac6dc3d629413',
      url_base: 'https://api.openweathermap.org/data/2.5/',
      query: '',
      weather:  {}
    }
  },

  methods: {
    fetchWeather (e){
      if (e.key  = "Enter"){
          fetch(`${this.api_base}weather?q=${this.query}&units=metrics&APPID=${this.api_key}`)
          .then(res => {
            return
          })
      }
    
  },

}
</script>

<style>
*{
margin: 0;
padding: 0;
box-sizing: border-box;
}
body{
 font-family: Arial, Helvetica, sans-serif;
}
#app{
background-image: url('./assets/night-bg.jpg');
background-size: cover;
background-position: bottom;
transition: 0.4s;
}

main{
min-height: 100vh;
padding: 25px;
background-image: linear-gradient(to bottom, rgba(0,0,0,0.25), rgbs(0,0,0,0.75));
}
.search-box{
width: 100%;
margin-bottom: 30px;

}
search-box .search-bar{
display: block;
width: 100%;
padding: 15px;
color: #313131;
font-size: 20px;

appearance: none;
border: none;
outline: none;

box-shadow: 0px 0px 0px ,rgba(0,0,0,0.25);
background-color:rgba(255,255,255,0.5);
border-radius:  0px 16px 0px 16px;
transition: 0.4s; 
}

.search-box .search-bar:focus{
  box-shadow: 0px 0px 16px rgba(0,0,0, 0.25);
  background-color: rgba(255,255,255,0.75);
  border-radius: 16px 0px 16px 0px;
}
.location-box .location{
  color: #FFF;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0,0,0, 0.25);
}
.location-box .date{
  color: #FFF;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
}
.weather-box{
 text-align: center;

}
.weather-box .temp{
 display: inline-block;
 padding: 10px 25px;
 color: #FFF;
 font-size: 102px;
 font-weight: 900;

 text-shadow: 3px 6px rgba(0,0,0, 0.25);
 background-color: rgba(255,255,255,0.25);
 border-radius: 16px ;
 margin: 30px 0px;
 box-shadow: 3px 6px rgba(0,0,0, 0.25);
}
.weather-box .weather{
color: #FFF;
font-size: 48px;
font-weight: 700;
font-style: italic;
text-shadow: 3px 6px rgba (0,0,0,0.25);

}
</style>
