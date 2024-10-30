<script>
   let {inputValue } = $props()

    let error = $state(false)
    const valorInput = (e) => {
    
        // console.log(`aaa`)
    }

    const handleSubmit = (e) => {
      e.preventDefault()
      //validar

      if(inputValue.ciudad.trim() === '' ){
        error = true
        return

    }
    console.log(inputValue.ciudad )

}
</script>
<h1>Formulario aqui</h1>

{#if error}
<p class="red darken-4 error">Todos los campos son obligatorios</p>


{/if}



<form action="" onsubmit={handleSubmit}>
    <div class="input-field col s12">
        <input type="text" name="ciudad" id="ciudad" bind:value={inputValue.ciudad} oninput={valorInput}>
        <label for="ciudad">Ciudad: </label>
    </div>  
    <!-- <div class="input-field col s12">
        <select name="pais" id="pais" onchange={valorInput} bind:value={inputValue.pais}>
            <option value=""> -- Seleccione un pais a-- </option>
            <option value="US">Estados Unidos</option>
            <option value="VE">Venezuela</option>
            <option value="MX">México</option>
            <option value="AR">Argentina</option>
            <option value="CO">Colombia</option>
            <option value="CR">Costa Rica</option>
            <option value="ES">España</option>
            <option value="PE">Perú</option>
        </select>
        <label for="pais">Pais</label>
    </div> -->

    <div class="input-field col s12">
        <input class="waves-effect waves-light btn-largue btn-block yellow accent-4" type="submit" value="Buscar Clima" >
    </div>
</form>