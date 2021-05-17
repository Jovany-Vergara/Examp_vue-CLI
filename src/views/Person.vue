<template>
  <div class="about">
    <h1>{{message}}</h1>
  <button v-on:click="imprimir" class="btn btn-warning mi_class">Guardar</button>
  <p>Se ha hecho clic en el botón de arriba {{ counter }} veces</p>
  <div class="row">
      <div class="col">
          Name:
      </div>
      <div class="col">
          <input type="text" v-model="person.name">
      </div>
<p></p>
      <div class="col">
          First Name:
      </div>
      <div class="col">
          <input type="text" v-model= "person.apellidos">
      </div>
      <p></p>

    <div class="col">
        Age:
    </div>
    <div class="col">
        <input type="text" v-model= "person.edad">
        
    </div>
  </div>
  <hr>
  <div class="row">
      <div class="col">
          Lista de personas
          <li>
              Persona Agregada: {{listPersonas }}
          </li>
      </div>
  </div>
  <hr>
  <div class="row">
      <div class="col">
          Persona Encontrada
          Indica Nombre: 
          <input type="text" v-model="nameToSearch">
          <button v-on:click="buscar">Buscar</button>
          <li>Encontrada: {{personFound}} </li>
      </div>
  </div>
  
  </div>
  
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Person',
  data: function() {
    return {
        person: {
            name: "",
            apellidos: "",
            edad: null,
            
        },
        counter: 0,
        message: "",
        listPersonas: [],
        nameToSearch: "",
        personFound: {}
    } 
  },
  methods: {
    imprimir: function(){
        console.log(this.person)
        this.listPersonas.push({...this.person})
    },
    buscar: function(){
        this.personFound =  this.listPersonas.find(personQueItera => personQueItera.name == this.nameToSearch)
    }

  },
  components: {
    
  }
}
</script>

<style lang="scss" scoped>

.mi_class {
    background-color: red;
}
</style>