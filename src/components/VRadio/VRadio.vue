<template>
  <div>
    <radio 
      :name="name"
      :checked="checked"
      @input="updateValue($event)"  
      :value="value">
      {{label}}
    </radio>
  </div>
</template>

<script>
import { Radio } from 'vue-checkbox-radio';

export default {
  components:{
    'radio': Radio
  },
  props: {
    name: {
      type: String,
      required: true
    },
    value: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true
    },
    checked: {
      type: Boolean,
      required: false,
      default: false
    }
  },
  methods: {
    updateValue: function(value){
      this.$emit('input', value);
    }
  }
}
</script>

<style>

</style>