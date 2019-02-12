<template>
	<div class="main">
      <lpanel :chose="3"></lpanel>
      <div class="loading">
        <div></div>
      </div>
   </div>
</template>

<script>
import lists from '~/components/lists.vue';
import lpanel from '~/components/lpanel.vue';

export default {
    
    components: {lists, lpanel},

    mounted(){     
      this.$router.push('/lists/0')
    },
}
</script>

<style scoped>
html, body {
    margin: 0;
    padding: 0;
}

.main {
  background-color: #000;
  display: flex;
  width: 100vw;
  position: relative;
  min-height: 100vh;
  position: absolute;
  flex-direction: row;
}
.loading {
  display: flex;
  justify-content: center;
  align-items: center;

  position: absolute;

  min-height: 100vh;
  min-width: calc(100%-70px);

  left: 70px;

  border-width: 20px;
  background-color: #e5e5e5;
}

.loading>div {
  background-color: white;

  height: 10em;
  width: 10em;

  border-radius: 50%;

  transition: 1s;

  animation-name: load;
  animation-duration: 5s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

@keyframes load {
  0% {height: 10em; width: 10em; background-color: rgba(140, 140, 240, 0.5)}
  25% {height: 5em; width: 5em; background-color: rgba(140, 240, 140, 0.5)}
  50% {height: 10em; width: 10em; background-color: rgba(240, 140, 140, 0.5)}
  75% {height: 5em; width: 5em; background-color: rgba(140, 140, 240, 0.5)}
  100% {height: 10em; width: 10em; background-color: rgba(140, 240, 140, 0.5)}
}
</style>