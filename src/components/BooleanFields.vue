<template>
  <!-- Com slide -->
  <div class="boolean-field">
      <span :class="['bg-selected', {switch: bluray}]"></span>
      <span class="option-name">Bluray</span>
      <div @click="toggleBluray(true)" class="button">Sim</div>
      <div  @click="toggleBluray(false)" class="button">Não</div>
  </div>
  <div class="boolean-field">
    <span :class="['bg-selected', {switch: temporary}]"></span>
    <span class="option-name">Temporary</span>
    <div @click="toggleTemporary(true)" class="button">Sim</div>
    <div @click="toggleTemporary(false)" class="button">Não</div>
  </div>
  <!-- Sem slide -->
  <div class="boolean-field">
    <span class="option-name">Filler</span>
    <div @click="toggleFiller(true)" :class="['button', {selected: filler}]">Sim</div>
    <div @click="toggleFiller(false)" :class="['button', {selected: !filler}]">Não</div>
  </div>
</template>

<script>
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
  components: {}
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
.option-name{
  background-color: #2d2a36;
  color: #ccc;
  padding: 2px 4px;
  position: absolute;
  left: 16px;
  top: -8px;
  box-shadow: 1px 1px 4px black;
  z-index: 2;
}
.button{
  width: 192px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.3s;
  cursor: pointer;
  z-index: 1;
}
/* Com slide */
.bg-selected{
  width: 192px;
  height: 48px;
  background-color: #3e3b4b;
  border-radius: 0 8px 8px 0;
  position: absolute;
  right: 0;
  z-index: 0;
  animation: slide-out 0.2s;
}
.switch{
  border-radius: 8px 0 0 8px;
  animation: slide-in 0.2s forwards;
}
@keyframes slide-out {
  from {
    left: 0;
  }
  to {
    left: 50%;
  }
}
@keyframes slide-in {
  from {
    left: 50%;
  }
  to {
    left: 0;
  }
}
/* Sem slide */
.boolean-field div:nth-child(2){
  border-radius: 8px 0 0 8px;
}
.boolean-field div:nth-child(3){
  border-radius: 0 8px 8px 0;
}
.selected{
  background-color: #3e3b4b;
}
</style>