<script>
  import Formulario from "./components/Formulario.svelte";
import Header from "./components/Header.svelte";
  import Pruebafetch from "./components/Pruebafetch.svelte";
  import DataClima from "./components/DataClima.svelte";
  import Spinner from "./components/Spinner.svelte";



let secondValue = $state([{
 
}])
let arrImg = $state({})

let spinner = $state(false)

let error = $state(false)

let inputValue = $state("")


    async function llamadoGiphy() {

    spinner = true

  setTimeout(() => {
    
   spinner = false
  }, 3000);
 

const cuatro = `https://api.weatherapi.com/v1/current.json?key=6a7fda08e4d2464f96e40303242810&q=${secondValue.valor}&aqi=no`;
// const cinco = `https://api.weatherapi.com/v1/current.json?key=6a7fda08e4d2464f96e40303242810&q=${inputValue}&aqi=no`;
// const url = `https://api.weatherapi.com/v1/current.json?key=6a7fda08e4d2464f96e40303242810&q=${inputValue}&aqi=yes`

const resp = await fetch(cuatro)
const data = await resp.json()


console.log(data)

const location = {
  names: data.location.name,
  estado : data.location.region,
  clima : data.current.condition.icon,
  tempC : data.current.temp_c,
  pais: data.location.country,
}

arrImg = location


    }
  
</script>

<main class="light-blue">
  <Header titulo = {`Clima App`}/>
  <div class="contenedor-form">
    <div class="container">
      <div class="row">
        <div class="col m6 s12">
          <Pruebafetch secondValue = {secondValue} arrImg={arrImg} llamadoGiphy={llamadoGiphy} error={error} inputValue={inputValue}/>
        </div>
        <div class="col m6 center s12 m">


         {#if error}
           <!-- content here -->
            <h1>PAPALOTE</h1>

          {:else if spinner}
          <Spinner/>
<p>Cargando datos...</p>
{:else}
   <DataClima secondValue = {secondValue} arrImg={arrImg} llamadoGiphy={llamadoGiphy} spinner={spinner} />
         {/if}

        
        </div> 
      </div>
    </div>


  

</main>


<style>
  main{
    height: 100dvh;
  }

  .m{
    color: white;
    font-weight: bold;
  }
</style>

