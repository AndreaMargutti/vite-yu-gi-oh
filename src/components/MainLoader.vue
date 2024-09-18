<!--Creo il componente-->
<script>
export default {
  data() {
    return {
      
    }
  }
}
</script>

<template>
    <div class="loader">
    </div>
</template>

<style scoped>
/*
Credits:  Temani Afif
Link: https://css-loaders.com/factory/
*/
.loader {
  width: 90px;
  height: 30px;
  box-shadow: 0 3px 0 #fff;
  --g:repeat-x repeating-linear-gradient(90deg,#ccc 0 16px,#0000 0 18px,#ccc 0 34px,#0000 0 100%);
  background: var(--g),var(--g);
  background-size: 60px 14px,60px 14px;
  animation: l8 1s infinite linear;
  position: relative;
  left: 50%;
  top: 50%;
}
@keyframes l8 {
  0%   {background-position:0    0,0    100%}
  100% {background-position:60px 0,60px 100%}
}
</style>