<script>    
    let {secondValue , llamadoGiphy, error , inputValue} = $props()
   

    const handleSubmit = (e) => {
    
      e.preventDefault()

     

     
      llamadoGiphy()
     
      secondValue.valor=""

    }

    
</script>






<form action="" onsubmit={handleSubmit}>
  <div class="input-field col  s12">
    <input type="text" name="" id="ciudad"  bind:value={secondValue.valor}>
<label for="ciudad">Ciudad: </label>
<input class="waves-effect waves-light btn-largue btn-block yellow accent-4 m" type="submit" name="" id="" value="Buscar Clima"> 
    </div>


</form>
<style>
  .m{
    outline: none;
    border: none;
    padding: 5px;
    border-radius: 10px;
  }
</style>