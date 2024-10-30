<script>

  let { arrImg,} = $props()


</script>


{#if Object.keys(arrImg).length > 0}
   <p>{arrImg.names}  {arrImg.estado}</p>
   <p>{arrImg.pais}</p>
   <figure>
     <img src={arrImg.clima} alt="">
   </figure>
   <p>{arrImg.tempC} <span> &#176&#67</span></p>

{/if}
