<template>

<div class="background">
    <img src="https://images.pexels.com/photos/1769743/pexels-photo-1769743.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" />
</div>

</template>

<style scoped>
.background img{
  position: fixed;
  top: 0;
  left: 0;
  min-height: 90%;
  min-width: 1500px;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: -2;
  object-fit: cover;
  -webkit-background-size:cover; -moz-background-size:cover; -o-background-size:cover; background-size: cover;
  filter: brightness(0.8);
}
</style>