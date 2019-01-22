<template>
	<div class="main">
    <div class="header">
      <img src="/coming.png" height="100%" class='marX'>
      <form class='marX'>
        <img src="/search.png" height="100%" >
        <input type="text" class="marX" placeholder="Поиск">
      </form>
      <button type="button" >Добавить</button>
    </div>
	</div>
</template>

<script>

</script>

<style scoped>
  .main {
    position: absolute;
    left: 70px;

    width: calc(100%-70px);
    min-height: 100%;
  
    background-color: rgb(240, 240, 240);
    background-image: url('/desk.jpg');
    background-size: cover;
    background-position: center;
    background-attachment: fixed;

    display: flex;
    flex-direction: column;
  }

  .marX {
    margin: 0 10px;
  }

  .main>.header {
    height: 4em;
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    padding: 10px;
  }

  .main>.header>form {
    background-color: white;

    width: 70%;
    height: 100%;

    border-radius: 5px;
    box-shadow: 5px rgba(0,0,0,0.5);

    padding: 5px;

    display: flex;
  }

  input:focus, input {
    border: none;
    outline: none;
  }

  .main>.header>form>input {
    width: 100%;
    height: 100%;

    font-size: 1.25em;
  }


</style>