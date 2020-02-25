<template>
  <div>
    <br/>
    {{data}}
    <my-input label="Teste" v-model="data" @testv="testeConsole"/>
    
    <hr/>

    {{dataRadio}}
    
    <p>
      <my-radio 
        name="robot" 
        value="Robo" 
        :checked="dataRadio === 'Robo'" 
        @input="(teste2) => this.dataRadio = teste2" 
        label="Robo" />
      <my-radio name="robot" value="Humano" :checked="dataRadio === 'Humano'" @input="(teste2) => this.dataRadio = teste2" label="Humano" />
    </p>
    
  </div>
</template>

<script>
import VInputTime from './components/VInput/VInput.vue';
import VRadio from './components/VRadio/VRadio.vue';

export default {
  name: 'app',
  components: {
    'my-input': VInputTime,
    'my-radio': VRadio
  },
  data () {
    return {
      data: 'Testes',
      teste: '',
      dataRadio: 'Humano'
    }
  },
  methods: {
    testeConsole(value){
      console.log(value);
    },
  }
}
</script>

<style lang="scss">
</style>
