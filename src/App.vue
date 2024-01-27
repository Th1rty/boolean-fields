<template>
  <div class="view">
    <BooleanFields
      @bluray="(bool) => bluray=bool"
      @temporary="(bool) => temporary=bool"
      @filler="(bool)=>filler=bool"
    />
  </div>
  <h2>- App.vue -</h2>
  <p>
    Bluray: {{ bluray }} <br>
    Temporary: {{ temporary }}<br>
    Filler: {{ filler }}
  </p>
</template>

<script>
import BooleanFields from '@/components/BooleanFields.vue'

export default {
  name: 'App',
  components: {
    BooleanFields
  },
  data() {
    return {
      bluray: false,
      temporary: false,
      filler: false,
    }
  },
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  user-select: none;
  -webkit-user-select: none;
}
body{
  background-color: #0d151a;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.view{
  display: flex;
  gap: 16px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
