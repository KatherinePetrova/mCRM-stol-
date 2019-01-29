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
            <svg height="50%" viewBox="0 0 29700 21000" class="strel">
              <polygon class="kras" points="18025.03,4030.83 22605.35,9720.39 18025.03,15721.18 24036.69,15721.18 28935.08,9778.26 24036.69,4030.83 "/>
              <polygon points="20914.57,9755.66 16238.84,4066.1 10099.96,4066.1 14680.26,9784.61 10163.58,15756.45 16207.04,15756.45 "/>
              <polygon points="13047.79,9840 8213.02,4092.57 2074.14,4092.57 2074.14,15782.92 8244.83,15782.92 "/>
            </svg>
          </div>
          <div class="option right">
            <svg height="50%" viewBox="0 0 29700 21000" class="pie">
                <path d="M14752.87 11377.49l10238.65 51.8c-33.96,5284.37 -4645.48,9545 -10300.13,9516.39 -5654.65,-28.61 -10211.12,-4335.63 -10177.17,-9620 33.96,-5284.37 4645.48,-9545 10300.13,-9516.39l-61.48 9568.2z"/>
                <path d="M15613.28 10253.77l107.01 -10085.81c5418.77,57.5 9763.65,4619.69 9704.54,10189.91l-9811.55 -104.1z"/>
            </svg>
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
      <div class="body">
        <div class="news">
          НОВЫЕ
          <div>2</div>
        </div>
        <div class="rows">
          <div>СЕЙЧАС</div>
          <div>ПЕРЕШЛИ В ЭТАП</div>
          <div>ПОТЕРЯННЫЕ</div>
        </div>
        <div class="step">
          <div class="body">
            <div class="content">
              Новая сделка
              <div>
                <div>135 сделок</div>
                <div>11105100 тг</div>
              </div>
            </div>
            <div class="content1">
              <div><font>25</font> сделок</div>
              <div>152 154 тенге</div>
            </div>
          </div>
          <div class="footer left">
            0 сделок, 0 тенге
          </div>
        </div>
      </div>
    </div>
    <div class="stat_tasks">
      <div class="block" style="color: rgb(255, 121, 121); border-top-color: rgb(255, 121, 121)">
        <div class="header">
          ПРОСРОЧЕННЫЕ ЗАДАЧИ
          <div>!</div>
        </div>
        <div class="content">
          6
          <div>
            <div style="font-size: 1.4rem">-13%</div>
            <div style="font-size: 0.8rem">Вчера: 8</div>
          </div>
        </div>
      </div>
      <div class="block" style="color: rgb(60, 60, 60); border-top-color: rgb(60, 60, 60)">
        <div class="header">
          ЗАДАЧИ К ВЫПОЛНЕНИЮ
        </div>
        <div class="content">
          675
          <div>
            <div style="font-size: 1.4rem">0%</div>
            <div style="font-size: 0.8rem">Вчера: 675</div>
          </div>
        </div>
      </div>
      <div class="block" style="color: rgb(60, 60, 60); border-top-color: #7dbe26">
        <div class="header">
          ВЫПОЛНЕННЫЕ ЗАДАЧИ
        </div>
        <div class="content">
          24
          <div>
            <div style="font-size: 1.4rem">+71%</div>
            <div style="font-size: 0.8rem">Вчера: 14</div>
          </div>
        </div>
      </div>
      <div class="block" style="color: rgb(60, 60, 60); border-top-color: #ffcc66">
        <div class="header">
          СДЕЛОК БЕЗ ЗАДАЧ
        </div>
        <div class="content">
          12783
          <div>
            <div style="font-size: 1.4rem">Сейчас</div>
          </div>
        </div>
      </div>
    </div>
    <div class="stat_body">
      <div class="sb_left">
        <div class="block" style="margin-right: 5px; background-color: white; padding: 10px">
          <div class="header">
            ИСТОЧНИКИ СДЕЛОК
          </div>
          <div class="pie">
            <div></div>
          </div>
        </div>
        <div class="block" style="margin-left: 5px">
          <div class="block" style="background-color: white"></div>
          <div class="block">
            <div class="block"></div>
            <div class="block"></div>
          </div>
        </div>
      </div>
      <div class="sb_right">

      </div>
    </div>
	</div>
</template>

<script>

</script>

<style scoped>

::-webkit-scrollbar {
	width: 4px;
}
::-webkit-scrollbar-track {
	background: #f1f1f1; 
}
::-webkit-scrollbar-thumb {
	background: #888; 
}
::-webkit-scrollbar-thumb:hover {
	background: #555; 
}

html, body {
  padding: 0;
  margin: 0;
}
  .main {
    

    width: 100%;
    min-width: 768px;
    min-height: 100vh;
  
    background-color: rgb(240, 240, 240);
    background-image: url('/desk.jpg');
    background-size: cover;
    background-position: center;
    background-attachment: fixed;

    display: flex;
    flex-direction: column;

    overflow-y: auto;

    padding-bottom: 2rem;
  }

  .marX {
    margin: 0 10px;
  }

  /* header */

  .main>.header {
    min-height: 4rem;
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
    min-height: 3rem;
    width: 100%;

    padding: 0;

    text-shadow: 1px 1px 1px black;

  }

  /* stat1 */
  
  .main>.stat1 {
    /* background-color: black; */

    height: 28rem;
    min-height: 28rem;
    width: 100%;

    padding: 5px 15px;

    display: flex;
    flex-direction: column;
    align-items: center;

    position: relative;
  }

  /* stat1>header1 */

  .main>.stat1>.header1 {
    min-height: 10%;
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

    min-height: 4.5rem;
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

    white-space: nowrap;
  }

  .main>.stat1>.header2>.chose>.option>svg.pie>path {
    fill: rgba(255, 255, 255, 0.5);
  }

  .main>.stat1>.header2>.chose>.option>svg.strel {
    margin-top: 2px;
  }
  .main>.stat1>.header2>.chose>.option>svg.strel>polygon {
    fill: rgba(255, 255, 255, 0.5);
  }

  .main>.stat1>.header2>.chose>.option:hover {
    color: white;
    border-color: white;
  }

  .main>.stat1>.header2>.chose>.option:hover svg.pie path {
    fill: white;
  }

  .main>.stat1>.header2>.chose>.option:hover svg.strel polygon {
    fill: white;
  }

  .main>.stat1>.header2>.chose>.active {
    color: white;
    border-color: white;
  }

  .main>.stat1>.header2>.chose>.active svg.pie path {
    fill: white;
  }

  .main>.stat1>.header2>.chose>.active svg.strel polygon {
    fill: white;
  }

  .main>.stat1>.header2>.chose>.left {
    border-bottom-left-radius: 3px;
    border-top-left-radius: 3px;
  }

  .main>.stat1>.header2>.chose>.right {
    border-bottom-right-radius: 3px;
    border-top-right-radius: 3px;
  }

  /* stat1>body */

  .main>.stat1>.body {
    /* background-color: black; */

    min-height: 20rem;
    height: 20em;
    width: 100%;
    min-width: 100%;

    display: flex;
    flex-direction: row;

    overflow-x: auto;

    border: solid 1px white;
    border-top: none;
    border-bottom: none;
    border-left: none;

    padding: 20px 0;
  }

  .main>.stat1>.body>.news {
    /* background-color: black; */

    min-width: 10%;
    width: 10%;
    height: 100%;

    color: rgba(255, 255, 255, 1);
    text-shadow: 1px 1px 1px rgba(200, 200, 200, 0.5);
    font-weight: 500;
    font-size: 0.8rem;

    display: flex;
    justify-content: center;
    flex-direction: column;

    border-right: solid 1px white;
  }

  .main>.stat1>.body>.news>div {
    font-size: 4rem;
  }

  .main>.stat1>.body>.rows {
    /* background-color: black; */

    min-width: 10%;
    width: 10%;
    height: 100%;

    color: rgba(255, 255, 255, 1);
    text-shadow: 1px 1px 1px rgba(200, 200, 200, 0.5);
    font-weight: 500;
    font-size: 0.8rem;

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    padding: 10px;
    padding-top: 3rem;
  }

  .main>.stat1>.body>.step {
    /* background-color: black; */

    min-width: 12rem;
    width: 12rem;
    height: 100%;

    color: rgba(255, 255, 255, 1);
    text-shadow: 1px 1px 1px rgba(200, 200, 200, 0.5);
    font-weight: 400;
    font-size: 1rem;

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    margin-right: 10px;
  }

  .main>.stat1>.body>.step>.body {

    min-height: 80%;
    height: 80%;
    width: 100%;

    border: solid 1px white;
    border-top: solid 7px rgb(194, 233, 88);

    padding-top: 5px;
    padding-bottom: 1rem;

    display: flex;
    flex-direction: column;
  }

  .main>.stat1>.body>.step>.body>.content {
    /* background-color: black; */

    min-height: 50%;
    height: 50%;
    width: 100%;
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    font-size: 1.1rem;
  }

  .main>.stat1>.body>.step>.body>.content>div {
    min-height: 50%;
    height: 50%;
    width: 100%;
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    font-size: 1rem;
  }

  .main>.stat1>.body>.step>.body>.content1 {
    min-height: 50%;
    height: 50%;
    width: 100%;
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    color: #36455a;

    background-color: white;
  }

  .main>.stat1>.body>.step>.body>.content1>div>font {
    /* margin-right: 5px; */
    font-size: 1.8rem;
  }

  .main>.stat1>.body>.step>.footer {
    min-height: 12%;
    height: 12%;
    width: 100%;

    border: solid 1px white;
    border-right-style: dashed;
    border-left-style: dashed;

    display: flex;
    justify-content: center;
    align-items: center;
  }

  .main>.stat1>.body>.step>.left {
    border-left-style: solid;
  }

  .main>.stat1>.body>.step>.right {
    border-right-style: solid;
  }

  /* stat_tasks */

  .main>.stat_tasks {
    /* background-color: black; */

    height: 12rem;
    min-height: 12rem;
    width: 100%;
    min-width: 100%;

    position: relative;

    padding: 5px 15px;

    display: flex;
    flex-direction: row;
  }

  .main>.stat_tasks>.block {
    height: 100%;
    min-height: 100%;
    width: 25%;
    min-width: 25%;

    background-color: white;

    border-right: solid 1px rgb(200, 200, 200);
    border-top: solid 5px rgb(194, 233, 88);

    padding: 5px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    font-size: 0.8em;
    font-weight: 700;
  }

  .main>.stat_tasks>.block>.header {
    /* background-color: black; */

    height: 15%;
    min-height: 15%;
    width: 100%;
    min-width: 100%;

    padding: 0 5px;

    display: flex;
    align-items: center;
  }

  .main>.stat_tasks>.block>.header>div {
    height: 0.9rem;
    width: 0.9rem;

    border-radius: 50%;
    background-color: rgb(255, 121, 121);
    margin-left: 10px;

    display: flex;
    justify-content: center;
    align-items: center;

    color: white;
  }

  .main>.stat_tasks>.block>.content {
    /* background-color: black; */

    min-height: 50%;
    height: 50%;
    width: 100%;

    display: flex;
    justify-content: space-between;
    align-items: center;

    font-size: 5rem;
    font-weight: 400;
  }

  .main>.stat_tasks>.block>.content>div {
    width: 40%;
    height: 100%;

    display: flex;
    flex-direction: column;
    justify-content: flex-end;

    font-size: 1rem;
    font-weight: 700;

    padding-bottom: 5px;
  }

  .main>.stat_tasks>.block>.content>div>div {

    display: flex;
    justify-content: flex-end;
  }

  /* stat_body */

  .main>.stat_body {
    /* background-color: black; */
    width: 100%;

    padding: 5px 15px;

    display: block;
  }

  .main>.stat_body>.sb_left {

    /* background-color: rgba(250,0,0,0.5); */

    min-width: 66.6%;

    float: left;

    display: block;
  }

  .main>.stat_body>.sb_left>.block {
    /* background-color: black; */

    height: 20rem;
    min-height: 20rem;
    width: calc(50% - 5px);

    float: left;

    display: flex;
    flex-direction: column;

    /* padding: 10px; */

    font-size: 0.8rem;
    font-weight: 700;

    justify-content: space-between;
    align-items: center
  }

  .main>.stat_body>.sb_left>.block>.header {

    height: 10%;
    min-height: 10%;
    width: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
  }

  .main>.stat_body>.sb_left>.block>.pie {
    background-color: rgb(71, 104, 250);

    width: 16rem;
    min-height: 16rem;
    height: 16rem;

    border-radius: 50%;

    display: flex;
    justify-content: center;
    align-items: center;
  }

  .main>.stat_body>.sb_left>.block>.pie>div {
    background-color: white;

    width: 15rem;
    min-height: 15rem;
    height: 15rem;

    border-radius: 50%;
  }

  .main>.stat_body>.sb_left>.block>.block {

    /* background-color: white; */

    height: calc(50% - 5px);
    min-height: calc(50% - 5px);
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .main>.stat_body>.sb_left>.block>.block>.block {
    height: 100%;
    min-height: 100%;
    width: calc(50% - 5px);

    background-color: white;
  }

  .main>.stat_body>.sb_right {
    background-color: rgba(0,0,250,0.5);
    
    min-width: calc(33.3% - 10px);

    float: left;

    display: block;
    
    margin-left: 10px;
  }

</style>