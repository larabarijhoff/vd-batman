<script>
  import Scroller from "@sveltejs/svelte-scroller";
  import {onMount} from "svelte";
  import DebugScroller from "./components/DebugScroller.svelte";
    
  let visible = false;

  onMount(() => {
    setTimeout(() => {
      visible = true;
    }, 5000); // 3000 ms = 3 segundos
  });
  
  /* Variables para el scroller1 - top comics */
  let count
  let index
  let offset
  let progress
  let top = 0.1
  let threshold = 0.5
  let bottom = 0.9

  /* Charts */
  let chartsTopComics = {
    0: "top_comics_01.png",
    1: "top_comics_02.png",
    2: "top_comics_03.png",
    3: "top_comics_04.png",
  }
</script>

  
<main>
  <head>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap" rel="stylesheet">
  </head>
  
  <header class:visible={visible}>
    <div id="logo">
      <img src="./public/images/iconos/cubo.svg" alt="logo de la empresa">
    </div>
    <h1>DataGeek</h1>
  </header>

  <div id="titulo" style="font-size: 40px" class:visible={visible}>
    <h1> La trayectoria de Batman: un ícono en la cultura geek</h1>
  </div>

  <div id="batman-container">
    <div id="brave"></div>
  </div>

  <div class = "dialogo-bruce"> 
    <img src="/images/batman-intro.png" alt="Presentacion Batman" class ="background">
    <img src="/images/batman-intro-dialogo.svg" alt="Presentacion Batman Dialogo" class = "overlay">
    
  </div>

  <!-- Primer scroller top comics-->
  <Scroller
    top={top}
    threshold={threshold}
    bottom={bottom}
    bind:count={count}
    bind:index={index}
    bind:offset={offset}
    bind:progress={progress}
  >
    <div slot="background" class="image_container">
      <img src="/images/graphs/{chartsTopComics[index]}" alt="chart {index}" class="charts"/>
    </div>
    <div slot="foreground" class="foreground_container">
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>Los tres cómics más vendidos de Batman</p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            The Dark Knight Returns una de las novelas gráficas más vendidas de todos los tiempos. Revolucionó a Batman 
            como un personaje oscuro y complejo, diferente al Batman más ligero de décadas anteriores. 
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            The Killing Joke es una novela gráfica famosa por su profunda exploración del Joker y su relación con Batman.
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            The Long Halloween es aclamada por su narrativa compleja y su exploración de los primeros años de Batman 
            como detective y aliado de Harvey Dent y Jim Gordon.
          </p>
        </div>
      </section>
    </div>
  </Scroller>

  <div class="linea">
    <section id="timeline">
      <h2 class="heading">Timeline de los eventos</h2>
      <ul>
        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2005</span>Batman Begins</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              Destaca por su exploración profunda de temas como el miedo, la justicia y la identidad.
              La película revitaliza el origen de Batman, mostrando la transformación de Bruce Wayne en el Caballero Oscuro.
              Se explora de manera detallada la lucha interna y motivaciones de Bruce Wayne. 
              Esta película coincide con la narrativa de cómics famosos como "Batman: Year One", "The Man Who Falls" y "The Long Halloween".
            </p>
            <button>Ver Comics</button>
          </div>
        </li>

        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2008</span>The Dark Knight</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              Explora temas de caos, moralidad y dualidad. La película profundiza en la lucha de Batman contra el Joker, 
              un agente del caos que desafía sus límites y principios. La relación entre Batman y 
              el Joker resalta la delgada línea entre el orden y la anarquía, coincidiendo con la 
              narrativa de cómics como "The Killing Joke".
            </p>
            <button>Ver Comics</button>
          </div>
        </li>
      
        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2012</span>The Dark Knight Rises</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              The Dark Knight Rises aborda temas de redención, sacrificio y resurgimiento. 
              La película muestra a Bruce Wayne enfrentando sus miedos y luchando por la salvación de Gotham. 
              La presencia de Bane y Talia al Ghul conecta con la serie de cómics "Knightfall" y 
              "No Man’s Land", destacando la perseverancia de Batman ante desafíos extremos.
            </p>
            <button>Ver Comics</button>
          </div>
        </li>
      </ul>
    </section>
  </div>
      
  
  <footer>
    <div class="footer-content">
      <p style="font-size: 20px;">CREDITS</p>
      <div class="credits">
        <p>Visual Editing</p>
        <p>Creative Director</p>
        <p>Data Manager</p>
      </div>
      <div class="credits-names">
        <p>Valentina Gayo</p>
        <p>Lara Barijhoff</p>
        <p>Camilo Suárez</p>
      </div>
      <p style="font-size: 20px;">SHARE</p>
      <div class="social-media-links">
        <img src="./images/iconos/facebook.svg" alt="Facebook">
        <img src="./images/iconos/twitter.svg" alt="Twitter">
        <img src="./images/iconos/whatsapp.svg" alt="Whatsapp">
      </div>
      <p style="font-size: 10px; color:gray; margin-right:30px; margin-left:30px; font-family: 'Open Sans', sans-serif;">At DataGeek, 
        we are passionate about sharing interesting and relevant content about geek culture. 
        We strive to provide you with the best possible experience, offering high-quality articles, 
        news, and analyses. We deeply appreciate your trust and support in our work. Our commitment is 
        to deliver accurate and entertaining information, enriching your knowledge and enjoyment of the geek world.</p>
      <p style="color: gray" class="copyright">&copy; 2024 DataGeek</p>
    </div>
  </footer>

</main>




<style>
  h1{
    color: #fff;
    font-family: 'Bebas Neue', sans-serif;
  }
  p{
    color: #fff;
    font-family: 'Comic Neue', sans-serif;
    font-size: 18px;
  }
  h3{
    font-family: 'Bebas Neue', sans-serif;
  }
  header {
    background-color: rgb(0, 12, 38,1);
    color: #fff;
    text-align: center;
    position: fixed;
    top: 0;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 999;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    opacity: 0;
    transition: opacity 1s;
  }
  header.visible {
    opacity: 1;
  }

  #logo{
    padding-right: 0.5%;
    padding-top: 0.6%;
  }

  #titulo{
    display: flex; 
    width: 100vw;
    justify-content: center; /* Centra horizontalmente */
    align-items: center; /* Centra verticalmente */
    text-align: center;
    margin-top: 7%;
    opacity: 0;
    transform: translateX(-100%);
    transition: transform 0s, opacity 0s; /* Transición instantánea */
  }
  #titulo.visible {
    opacity: 1;
    transform: translateX(0);
    transition: transform 0.5s, opacity 0.5s; /* Transición de 0.5 segundos */
  }

  #batman-container {
    width: 100vw;
    height: 58vh;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    /* margin-top: 5%; */
  }

  #brave {
    width: 350px;
    height: 350px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  #brave:before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background: #ffffff;
    border-radius: 50%;
    animation: m 4s .5s both;
  }

  #brave:after {
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      background: #000;
      clip-path: polygon(52% 10%, 48% 10%, 47% 2%, 45% 16%, 46% 23%, 29% 32%, 26% 39%, 12% 100%, 88% 100%, 74% 39%, 71% 32%, 54% 23%, 55% 16%, 53% 2%);
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 2;
  }

  @keyframes m {
      0% { transform: translate(-400%, 10%); }
      40% { transform: translate(-200%, -30%); }
      60% { transform: translate(-130%, 30%); }
      95% { transform: translate(-20%, -70%); }
      100% { transform: translate(0%, -5%); } 
  }

  .heading {
    margin-left: 30px;
  }

  /* Estilos para el scroller */
  .foreground_container {
    pointer-events: none;
    /* padding-left: 50%; */
  }
  .step_foreground {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    /* border: 1px solid rgba(0, 0, 0, 0.4); */
    color: white;
    padding: 1em;
    margin: 0 0 2em 0;
  }
  .epi_foreground {
    padding: 20px;
    width: 400px;
    background-color: rgba(255, 255, 255, 0.95);
    text-align: center;
  }
  .epi_foreground p {
    color: #000;
  }
  .image_container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
  }
  .image_container img {
    width: 950px;
  }

  #timeline ul li.blue-box .box .title{
    background-color: #1F4389;
  }

  #timeline .title {
    padding: 1rem 0rem 1rem 0.7rem;
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    color: #fff;
    font-size: 1.3rem;
  }

  #timeline .year {
    background-color: #fff;
    padding: 0.2rem 0.8rem;
    border-radius: 10px;
    color: #1F4389;
    font-size: 0.9rem;
    margin: 0 0.5rem;
  }

  #timeline p{
    padding-right: 1rem;
    padding-left: 1rem;
    color: #000;
  }

  #timeline button{
    margin: 0.2rem 0rem 0.5rem 0.5rem;
    border: 1px solid #ddd;
    padding: 0.2rem 0.5rem;
    visibility: hidden; 
  }


  #timeline ul {
    padding: 50px 0;
  }

  #timeline ul li {
    list-style: none;
    position: relative;
    width: 7px;
    margin: 0 auto;
    padding-top: 50px;
    background-color: #F6B83B;
  }

  #timeline ul li .box {
    position: relative;
    bottom: 0;
    width: 450px;
    background-color: #fff;
    box-shadow: 0 0 5px rgba(0,0,0,0.5);
    border-radius: 5px;
    /*transform: translateX(400%); para cuando quiera usar el scroll, primero desaparecerlo*/
  }

  /* derecha*/
  #timeline ul li:nth-child(odd) .box{
    left: 50px;
  }
  /*izquierda*/
  #timeline ul li:nth-child(even) .box{
    left: -500px;
  }
  /* Esto es para hacerlo aparecer con el scroll
  #timeline ul li .box.show {
    transform: translateX(0%);
    transition: all 0.5s ease-in-out;
  }
  */

  #timeline ul li i {
    position: absolute;
    left: 50%;
    top: 20%;
    width: 45px;
    height: 45px;
    background: #1F4389;
    transform: translateX(-50%);
    border-radius: 50%;
  }

  #timeline ul li.blue-box i {
      background-color: #fff; 
  }


  /*pico*/
  #timeline ul li .box:before {
    content: "";
    position: absolute;
    top: 5px;
    width: 0;
    height: 0;
    border-style: solid;
  }

  #timeline ul li.blue-box:nth-child(odd) .box:before {
      left: -15px;
      border-width: 8px 16px 8px 0;
      border-color: transparent #1F4389 transparent transparent;
  }
  #timeline ul li.blue-box:nth-child(even) .box:before {
      right: -15px;
      border-width: 8px 0 8px 16px;
      border-color: transparent transparent transparent #1F4389;
  }

 
  .dialogo-bruce{
    position: relative;
    width: 100%;  /* Ajusta el ancho según sea necesario */
    height: 700px; /* Ajusta la altura según sea necesario */
    margin-top: 4%;
  }

  .background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
  }

  .overlay {
    position: absolute;
    top: 100px;   
    left: 90px;   /* Ajusta la posición según sea necesario */
    width: 550px; /* Ajusta el tamaño según sea necesario */
    height: 300px; /* Ajusta el tamaño según sea necesario */
    z-index: 2;   /* Asegura que esta imagen esté por encima de la de fondo */
  }


  footer {
    background-color: #1F4389;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.7); 
    margin-top: 50px;
  }
  .footer-content {
    color: white;
    padding-top: 20px;
    text-align: center;
    letter-spacing: 2px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  
  .social-media-links img {
    width: 30px;
    height: auto;
    margin-right: 10px;
    margin-bottom: 30px;
  }
  .credits p {
    margin: 0 40px;
    display: inline-block;
    font-weight: bold;
    letter-spacing: 4px;
  }
  .credits-names p {
    margin: 0 4vw;
    display: inline-block;
    padding-bottom: 30px; 
    letter-spacing: 2px;
    font-weight: lighter;
    color: grey;
  }

</style>
