<template>
  <div>
    <div class="square"></div>
    <div class="circle"></div>
    <div class="triangle-up"></div>
  </div>
</template>

<style>
.square {
  height: 50px;
  width: 50px;
  background-color: #555;
}
.circle {
  height: 50px;
  width: 50px;
  background-color: #555;
  border-radius: 50%;
}
.triangle-up {
  width: 0;
  height: 0;
  border-left: 25px solid transparent;
  border-right: 25px solid transparent;
  border-bottom: 50px solid #555;
}
</style>
<script>
export default {}
</script>

