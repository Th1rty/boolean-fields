<template>
    <div :class="['button',{selected: selected}]">
      <slot />
    </div>
</template>

<script>
export default {
  name: 'BooleanButton',
  props: {
    selected: {
      type: Boolean,
      default: false
    },
  }

}
</script>

<style scoped>
.button{
  width: 192px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.3s;
}
.selected{
  background-color: #3e3b4b;
}
</style>