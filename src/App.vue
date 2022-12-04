<!-- note: api:- https://openweathermap.org/api -->

<template>
  <div class="app">
    <div class="display">
      <main>
        <div class="search-box">
          <input 
            type="text" 
            class="search-bar" 
            placeholder="Search..." 
            v-model="query"
            @keypress="fetchWeather"
          />
        </div>

        <div class="wather-wrap">
          <div class="location-box">
            <div class="location">Northampton, UK</div>
            <div class="date">Monday 20 January 2020</div>
          </div>

          <div class="weather-box">
            <div class="temp">9&#8451;</div>
            <div class="weather">Rain</div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      api_key: "d8ba05a0595a415733fdc530f31ccae6",
      url_base: "",
      query: '',
      weather: {},
    };
  },
  methods: {
    fetchWeather(e) {
      if(e.key == 'Enter') {
        console.log("enter");
      }
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: arial, sans-serif;
}

.app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  height: 100vh;
}

.display {
  background-image: url("./assets/cold-bg.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;

  /* max-width: 600px; */
  max-height: 800px;
}

main {
  min-height: 100%;
  padding: 25px;

  background-image: linear-gradient(
    to right,
    rgba(0, 0, 0, 0.25),
    rgba(0, 0, 0, 0.75)
  );
}

.search-box {
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar {
  display: block;
  width: 100%;
  padding: 15px;

  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  outline: none;
  background: none;

  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0 16px;
  transition: 0.4s;
}

.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 16px 0px 16px 0px;
}

.location-box .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}

.location-box .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weather-box {
  text-align: center;
}

.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;

  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box .weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
