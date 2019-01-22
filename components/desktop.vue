<template>
	<div class="main">
    <div class="header">
      <img src="/coming.png" height="100%" class='marX'>
      <form class='marX'>
        <img src="/search.png" height="100%" >
        <input type="text" class="marX" placeholder="Поиск">
      </form>
      <button type="button" class="marX">Добавить</button>
      <div><img class="time" src="time.png" height="100%"></div>
    </div>
    <div class="title">
      Тестовая компания
    </div>
    <div class="stat1">
      <div class="header1">
        <div class="chose">
          <div class="option active">
            Все
          </div>
          <div class="option">
            Мои
          </div>
          <div class="option" style="margin-left: 30px;">
            Менеджер
          </div>
        </div>
        <div class="chose">
          <div class="option active" style="margin-right: 15px;">
            Сегодня
          </div>
          <div class="option" style="margin-right: 15px;">
            Неделя
          </div>
          <div class="option" style="margin-right: 15px;">
            Месяц
          </div>
        </div>
        <div class="setting">
          <img src="/gear.png" style="margin-right: 5px" height="50%">
          Настроить
        </div>
      </div>
      <div class="lineX"></div>
      <div class="header2">
        <div class="chose">
          <div class="option left active">
            Але
          </div>
          <div class="option right">
            Але
          </div>
        </div>
        <div class="chose" style="margin-right: 25%">
          <div class="option left active">
            Отдел сервиса РК
          </div>
          <div class="option">
            Колл-центр
          </div>
          <div class="option">
            ДИП Анастасия
          </div>
          <div class="option">
            ДИП Евгения
          </div>
          <div class="option">
            На разработке
          </div>
          <div class="option right">
            Логистика Максим
          </div>
        </div>
      </div>
    </div>
	</div>
</template>

<script>

</script>

<style scoped>

html, body {
  padding: 0;
  margin: 0;
}
  .main {
    position: absolute;
    left: 70px;

    width: calc(100%-70px);
    min-width: calc(1024px -70px);
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

  /* header */

  .main>.header {
    height: 4rem;
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    padding: 15px;
    margin-top: 20px;
  }

  .main>.header>form {
    background-color: white;

    width: 70%;
    height: 100%;

    border-radius: 2px;
    box-shadow: 5px rgba(0,0,0,0.5);

    padding: 5px;

    display: flex;
  }

  input:focus, input, button {
    border: none;
    outline: none;
  }

  .main>.header>form>input {
    width: 100%;
    height: 100%;

    font-size: 1.25em;
  }

  .main>.header>button {
    height: 100%;
    width: 6em;

    border-radius: 2px;
    box-shadow: 5px rgba(0,0,0,0.5);

    background-color: #2290cf;

    font-size: 1em;
    color: white;

    cursor: pointer;
  }

  .main>.header>button:active {
    margin-top: 2px;
  }

  .main>.header>div {
    border: solid 1px white;

    padding: 7px;

    height: 2em;
    width: 2em;

    border-radius: 2px;

    cursor: pointer;
  }
  
  /* title */

  .main>.title {
    display: flex;
    justify-content: center;
    align-items: center;

    color: white;
    font-size: 1.75em;

    height: 3rem;
    width: 100%;

    padding: 0;

    text-shadow: 1px 1px 1px black;
  }

  /* stat1 */
  
  .main>.stat1 {
    /* background-color: black; */

    height: 25rem;
    min-height: 25rem;
    width: 100%;

    padding: 5px 15px;

    display: flex;
    flex-direction: column;
    align-items: center;

    position: relative;
  }

  /* stat1>header1 */

  .main>.stat1>.header1 {
    height: 10%;
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .lineX {
    height: 0;
    width: calc(100% + 30px);
    border-bottom: solid 1px white;
  }

  .main>.stat1>.header1>.chose {
    height: 100%;

    display: flex;
    flex-direction: row;
  }

  .main>.stat1>.header1>.chose>.option {
    height: calc(100% - 2px);

    margin-right: 5px;

    display: flex;
    justify-content: center;
    align-items: center;

    color: rgba(255, 255, 255, 0.5);

    cursor: pointer;
  }

  .main>.stat1>.header1>.chose>.option:hover {
    color: white;
  }

  .main>.stat1>.header1>.chose>.active {
    height: 100%;

    border-bottom: solid 2px white;

    color: white;
  }

  .main>.stat1>.header1>.setting {
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;

    color: rgba(255, 255, 255, 0.5);

    cursor: pointer;

    margin-left: 7%;
  }

  .main>.stat1>.header1>.setting>img {
    transition: 0.5s;
  }

  .main>.stat1>.header1>.setting:hover {
    color: white;
  }

  .main>.stat1>.header1>.setting:hover img {
    transform: rotate(90deg);
  }

/* stat1>header2 */

  .main>.stat1>.header2 {
    /* background-color: black; */

    height: 4.5rem;
    width: 100%;

    padding: 1.25rem 0;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .main>.stat1>.header2>.chose {
    height: 100%;

    display: flex;
    flex-direction: row;
  }

  .main>.stat1>.header2>.chose>.option {
    height: 100%;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    border: solid 1px rgba(255, 255, 255, 0.5);

    padding: 0 7px;

    color: rgba(255, 255, 255, 0.5);
    font-weight: 500;
    text-shadow: 1px 1px 1px rgba(200, 200, 200, 0.5);

    cursor: pointer;

    margin-left: -1px;
  }

  .main>.stat1>.header2>.chose>.active {
    color: white;
    border-color: white;
  }

  .main>.stat1>.header2>.chose>.option:hover {
    color: white;
    border-color: white;
  }

  .main>.stat1>.header2>.chose>.left {
    border-bottom-left-radius: 3px;
    border-top-left-radius: 3px;
  }

  .main>.stat1>.header2>.chose>.right {
    border-bottom-right-radius: 3px;
    border-top-right-radius: 3px;
  }

</style>