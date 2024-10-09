<template>
  <div id="app">
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="tituloTarjeta" />
      </div>

      <div>
        <label>Chip SRC: </label>
        <select v-model="numeroChip" required>
          <option value="" disabled selected>Elige tu opcion</option>
          <option value="1">chip.png</option>
        </select>
      </div>

      <div>
        <label>Número: </label>
        <input v-model="numeroTarjeta" placeholder="xxx xxx xxx xxx"/>
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" type="month" min="2024-10"/>
      </div>

      <div>
        <label>Propietario: </label>
        <input v-model="propietario" />
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <select v-model="numeroTipoTarjeta" required>
          <option value="" disabled selected>Elige tu opcion</option>
          <option value="1">Visa</option>
        </select>
      </div>
    </form>
    <div class="carnet">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40" :src="chipSRC[numeroChip]" alt="" />
      <div>
        <h2>{{ numeroTarjeta }}</h2>
        <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer>
        <span>{{ propietario }}</span>
        <img :src="tipoTarjeta[numeroTipoTarjeta]" width="60" />
      </footer>
    </div>
  </div>
  
</template>

<script>
export default {
  name: 'Formulario',
  props:{
    
  },
  data() {
    return {
      tituloTarjeta: '',
      numeroChip:'',
      chipSRC: ['','./src/assets/img/chip.png'],
      numeroTarjeta: '',
      fechaExpiracion: '',
      propietario:'',
      numeroTipoTarjeta:'',
      tipoTarjeta:['','./src/assets/img/visa.png']
    };
  }
};
</script>

<style scoped>
select:required:invalid {
  color: gray;
}
option[value=""][disabled] {
  display: none;
}
option {
  color: black;
}
</style>