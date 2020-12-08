<template>
  <form class="home" @submit.prevent='procesarFormulario'>
    <input type='text' placeholder='Ingrese nombre' v-model.trim='task.name'/>
    <div>
        <label for='checkbox1'>JS</label>
        <input type='checkbox' id='checkbox1' value='js' v-model='task.categorias'/>
    </div>
    <div>
        <label for='checkbox2'>NodeJS</label>
        <input type='checkbox' id='checkbox2' value='node' v-model='task.categorias'/>
    </div>

    <div>
      <div>
        <label for='radio1'>Urgente</label>
        <input type='radio' id='checkbox2' value='urgente' v-model='task.urgent'/>
      </div>
       <div>
        <label for='radio2'>Relax</label>
        <input type='radio' id='checkbox2' value='no urgente' v-model='task.urgent'/>
      </div>
    </div>
    <div>
      <input type='number' v-model.number='task.numero'/>
    </div>
  <p>
    {{task}}
  </p>

  <button type='submit' :disabled='bloquear'>Procesar</button>
  </form>


</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data(){
    return{
      task:{
        name:'',
        categorias:[],
        urgent:'',
        numero:''
    }
  }
},
methods:{
  procesarFormulario(){
  if(this.task.name === ''){
    console.log('vacio');
    return
  }
    this.task= {
        name:'',
        categorias:[],
        urgent:'',
        numero:''
    }
  }
},
computed:{
  bloquear(){
    return this.task.name.trim() === "" ? true : false
  }
}
}
</script>
