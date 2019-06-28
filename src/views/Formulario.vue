<template>
  <div class="mt-5">
    <h1>Formularios</h1>

    <form>
      <b-row>
        <b-col md="3">
          <!--  satate cambia estilo del input con la función comprobar -->
          <b-form-input type="text" v-model="texto" :state="comprobar"></b-form-input>
          <small>Minimo 3 caracteres</small>
          <p>texto: {{texto}}</p>
        </b-col>

        <b-col md="3">
          <b-form-select v-model="select" :options="animales"></b-form-select>
          <small>Selección : {{select}}</small>
        </b-col>

        <b-col md="3">
          <b-form-radio-group v-model="radio" :options="animales"></b-form-radio-group>
          <small>Selección : {{radio}}</small>
        </b-col>

        <b-col md="3" >

          <b-form-checkbox-group
           v-model="selected" 
           :options="animales">
           </b-form-checkbox-group>
           <small>Selección : {{selected}}</small>

        </b-col>
      </b-row>
      <!-- number : Solo permite el ingreso de numeros -->
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      texto: "",
      select: null,
      animales: [
        { value: null, text: "Seleccione a un animal" },
        { value: "Pato", text: "Cuak" },
        { value: "Gato", text: "Miau" },
        { value: "Perro", text: "Guau" }
      ]
    };
  },
  computed: {
    comprobar() {
      return this.texto.length > 2 ? true : false;
    }
  }
};
</script>