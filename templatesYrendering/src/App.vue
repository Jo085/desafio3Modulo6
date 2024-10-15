<script>
export default{
name: "App",
  data(){
    return{
      colorDeFondo: "white",
      colorDeTexto: "",
      mostrarTexto: false,
      borde: "",
      contenidoTexto: "Holaa",
      tipografia: "",
      fuentes: [ "cursive", "serif", "fantasy", "monospace" ],
      opaco: false,
      tamanoLetra: "",      
    };
  },
};
</script>

<template>

  <div>
    <!-- FORMULARIO -->
     <form class="py-3 px-4 bg-primary-subtle fs-6 rounded-3 shadow">
        <div class="d-flex flex-column justify-content-start  mb-3">
        <!-- COLOR DE FONDO -->
          <label class="mb-1">Color de fondo </label>
          <input v-model="colorDeFondo" >
        </div>
        <div class="d-flex flex-column justify-content-start  mb-3 ">
        <!-- COLOR DE TEXTO -->
          <label class="mb-1">Color de texto </label>
          <input v-model="colorDeTexto" >

        </div>
        <div class="d-flex justify-content-start  mb-3">
         <!-- MOSTRAR TEXTO --> 
          <label class="me-2"> Mostrar texto</label>
          <input type="checkbox" v-model="mostrarTexto" >

        </div>
        <div class="d-flex flex-column justify-content-start  mb-3">
         <!-- BORDE -->
          <label class="me-2"> Borde </label>
          <input type="range" v-model="borde">

        </div>
        <div class="d-flex flex-column justify-content-start  mb-3">
        <!-- CONTENIDO TEXTUAL -->
          <label class="me-2">Contenido textual </label>
          <textarea class="row-2" v-model="contenidoTexto"></textarea>

        </div>
        <div class="d-flex flex-column justify-content-start  mb-3">
        <!-- TIPOGRAFÍA -->
          <label class="me-2"> Tipografía </label>
          <select v-model="tipografia">
            <option v-for="fuente in fuentes">{{ fuente }}</option>
          </select>

        </div>
        <div class="d-flex justify-content-start  mb-3">
        <!-- OPACIDAD -->
          <label class="me-2"> Opaco </label>
          <input type="checkbox" v-model="opaco">

        </div>
        <div class="d-flex flex-column justify-content-start  mb-3">
         <!-- TAMAÑO LETRA -->
          <label class="me-2 mb-1">Tamaño de letra</label>
            <div class="d-flex">             
                <!-- OPCIONES DE TAMAÑO -->
              <label class="d-flex lign-items-center ms-2">
                  <input class="me-1" type="radio" value="1rem" v-model="tamanoLetra" >Pequeño
              </label>
              <label class="d-flex lign-items-center ms-2">
                  <input class="me-1" type="radio" value="2rem" v-model="tamanoLetra" > Mediano
              </label>
              <label class="d-flex lign-items-center ms-2">
                  <input class="me-1" type="radio" value="3rem" v-model="tamanoLetra"> Grande
              </label>
              
            </div>          
        </div>
     </form>
  </div>

  <!-- FIGURA -->
  <div :style="{ background: colorDeFondo,
       borderRadius: borde + 'px'
       }" 
       :class="{
          'opacidad': opaco,
       }"
       id="figura">
   
       <!-- texto -->
      <h3 v-show="mostrarTexto"
      :style="{
         color: colorDeTexto,         
         fontFamily: tipografia,
         fontSize: tamanoLetra,
         }"> 
        {{ contenidoTexto }}        
      </h3>     
  </div>

</template>

<style scoped>

.opacidad{
  opacity: 50%;
}

#figura{  
  width: 300px;
  height: 300px;  
  display: flex;  
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 3rem; 
  box-shadow: 0px 8px 8px 0px rgba(143,141,143,1);
}

</style>
