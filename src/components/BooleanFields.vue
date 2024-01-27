<template>
<div class="boolean-field">
    <span>Bluray</span>
    <BooleanButton :selected="bluray" @click="toggleBluray(true)">Sim</BooleanButton>
    <BooleanButton :selected="!bluray" @click="toggleBluray(false)">Não</BooleanButton>
</div>
  <div class="boolean-field">
    <span>Temporary</span>
    <BooleanButton :selected="temporary" @click="toggleTemporary(true)">Sim</BooleanButton>
    <BooleanButton :selected="!temporary" @click="toggleTemporary(false)">Não</BooleanButton>
  </div>
  <div class="boolean-field">
    <span>Filler</span>
    <BooleanButton :selected="filler" @click="toggleFiller(true)">Sim</BooleanButton>
    <BooleanButton :selected="!filler" @click="toggleFiller(false)">Não</BooleanButton>
  </div>
</template>

<script>
import BooleanButton from './BooleanButton.vue';
export default {
  name: 'BooleanFields',
  data(){
    return {
      bluray: false,
      temporary: false,
      filler: false
    }
  },
  props: {},
  methods: {
    toggleBluray(value){
      if (this.bluray !== value) {
        this.bluray = value
        this.$emit('bluray', value)
      }
    },
    toggleTemporary(value){
      if (this.temporary !== value) {
        this.temporary = value
        this.$emit('temporary', value)
      }
    },
    toggleFiller(value){
      if (this.filler !== value) {
        this.filler = value
        this.$emit('filler', value)
      }
    },
  },
  components: {
    BooleanButton
  }
}
</script>

<style scoped>
.boolean-field{
  width: 384px;
  height: 48px;
  background-color: #2d2a36;
  color: #888;
  display: flex;
  justify-content: space-between;
  align-content: center;
  border-radius: 8px;
  position: relative;
}
.boolean-field div:nth-child(2){
  border-radius: 8px 0 0 8px;
}
.boolean-field div:nth-child(3){
  border-radius: 0 8px 8px 0;
}
span{
  background-color: #2d2a36;
  color: #ccc;
  padding: 2px 4px;
  position: absolute;
  left: 16px;
  top: -8px;
  box-shadow: 1px 1px 4px black;
}
</style>