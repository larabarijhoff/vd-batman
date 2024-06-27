<script>
  import Scroller from "@sveltejs/svelte-scroller";
  import { onMount } from "svelte";
  import DebugScroller from "./components/DebugScroller.svelte";

  let visible = false;

  onMount(() => {
    setTimeout(() => {
      visible = true;
    }, 5000); // 3000 ms = 3 segundos
  });

  /* Variables para el scroller 1 - top comics */
  let count;
  let index;
  let offset;
  let progress;
  let top = 0.1;
  let threshold = 0.5;
  let bottom = 0.9;

  /* Variables para el scroller 2 - recaudacion pelis */
  let count2;
  let index2;
  let offset2;
  let progress2;
  let top2 = 0.1;
  let threshold2 = 0.5;
  let bottom2 = 0.9;

  /* Charts */
  let ventasTopComics = {
    0: "top_comics_01.png",
    1: "top_comics_02.png",
    2: "top_comics_03.png",
    3: "top_comics_04.png"
  };
  let recaudacionPeliculas = {
    0: "recaudacion_pelis_01.png",
    1: "recaudacion_pelis_02.png",
    2: "recaudacion_pelis_03.png",
    3: "recaudacion_pelis_04.png",
    4: "recaudacion_pelis_05.png"
  };

  // lara intento lluvia

  let canvas;
  let ctx;

  // Estructura de datos para las gotas de lluvia
  let raindrops = [];

  // Función para crear una nueva gota de lluvia
  function createRaindrop() {
    return {
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      speed: Math.random() * 7 + 5, // Aumentar la velocidad
      angle: Math.random() * 0.1 - 0.05 // Inclinación de la caída
    };
  }

  // Función para dibujar la lluvia
  function drawRain() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = 'rgba(255,255,255,1)';  // Cambiar a blanco completo
    ctx.strokeStyle = 'rgba(255,255,255,1)';  // Cambiar a blanco completo
    ctx.lineWidth = 3;
    ctx.lineCap = 'round';

    raindrops.forEach((drop) => {
      ctx.beginPath();
      ctx.moveTo(drop.x, drop.y);
      ctx.lineTo(drop.x - 6, drop.y + 8); // Gotas inclinadas a 45 grados hacia la izquierda
      ctx.stroke();

      drop.y += drop.speed;
      drop.x -= drop.speed; // Movimiento a 45 grados hacia la izquierda
      if (drop.y > canvas.height || drop.x < 0) {
        drop.x = Math.random() * canvas.width;
        drop.y = Math.random() * canvas.height; // Reiniciar la posición verticalmente aleatoria
        drop.speed = Math.random() * 7 + 5; // Restablecer velocidad
      }
    });

    requestAnimationFrame(drawRain);
  }

  onMount(() => {
    // Asegurarse de que el canvas se ajuste al tamaño del contenedor
    canvas.width = canvas.clientWidth;
    canvas.height = canvas.clientHeight;

    ctx = canvas.getContext('2d');

    // Crear 100 gotas de lluvia iniciales
    for (let i = 0; i < 300; i++) {
      raindrops.push(createRaindrop());
    }

    // Iniciar la animación de la lluvia
    drawRain();
  });

  // Ajustar el tamaño del canvas si la ventana cambia de tamaño
  window.addEventListener('resize', () => {
    if (canvas) {
      canvas.width = canvas.clientWidth;
      canvas.height = canvas.clientHeight;
    }
  });
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
      <img src="/images/iconos/cubo.svg" alt="logo de la empresa">
    </div>
    <h1>DataGeek</h1>
  </header>

  <div id="titulo" style="font-size: 35px" class:visible={visible}>
    <h1 style="margin: 5%;"> La trayectoria de Batman: un ícono en la cultura geek</h1>
  </div>

  <div id="batman-container">
    <div id="brave"></div>
  </div>

  <div class = "dialogo-bruce"> 
    <img src="/images/batman-intro.png" alt="Presentacion Batman" class ="background">
    <img src="/images/batman-intro-dialogo.svg" alt="Presentacion Batman Dialogo" class = "overlay">
    
  </div>

  <div class="sección-nueva">
    <h2>LOS INICIOS</h2>
    <p style="margin-bottom: 6.5vh;">
        Batman es un personaje ficticio publicado por DC Comics. Éste héroe fue creado por el artista 
        Bob Kane y el escritor Bill Finger, haciendo su primera aparición en Detective Comics #27 en 
        mayo de 1939. A lo largo de los años, la cantidad de publicaciones de cómics de Batman fue 
        aumentando, reflejando el incremento en el interés de dicho personaje.
    </p>
  </div>
  <div class="text-image-container">
    <div class="text-overlay">
        <p>
            Desde su debut, los cómics de Batman se publicaron mensualmente, sumando aproximadamente 12 números por año. 
            Este patrón se mantuvo durante décadas, consolidando a Batman como figura regular en las tiendas de cómics.
        </p>
        <br>
        <p>
            En las décadas de 2000 y 2010, el número de títulos de Batman aumentó debido a su popularidad continua y 
            la expansión de su universo con múltiples líneas narrativas y spin-offs.
        </p>
    </div>
    <img src="images/batman-inicios.png" alt="Batman Inicios" class="image">
</div>
  <!-- Primer scroller top comics -->
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
      <img src="/images/graphs/{ventasTopComics[index]}" alt="chart {index}" class="charts"/>
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
            El Caballero de la Noche Regresa una de las novelas gráficas más vendidas de todos los tiempos. Revolucionó a Batman 
            como un personaje oscuro y complejo, diferente al Batman más ligero de décadas anteriores. 
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            La Broma Asesina es una novela gráfica famosa por su profunda exploración del Joker y su relación con Batman.
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            La Larga Halloween es aclamada por su narrativa compleja y su exploración de los primeros años de Batman 
            como detective y aliado de Harvey Dent y Jim Gordon.
          </p>
        </div>
      </section>
    </div>

  </Scroller>

 
  <!-- HTML para representar las gotas de lluvia -->
  <div class="container-lluvia">
    <img src="/images/bat_lluvia.jpg" alt="Batman bajo la lluvia" class="bat-im">
    <canvas bind:this={canvas}></canvas>
  </div>


  <div class="sección-nueva">
    <h2>DE LOS CÓMICS A LA PANTALLA GRANDE y más</h2>
    <p>
      Llegar a los cines ya fue un logro que implicó mayor diversificación y alcance a las masas, 
      generando contenido nuevo para fanaticos fieles como para nuevos seguidores.
    </p>
  </div>

  <!-- Segundo scroller recaudacion pelis-->
  <Scroller
    top={top2}
    threshold={threshold2}
    bottom={bottom2}
    bind:count={count2}
    bind:index={index2}
    bind:offset={offset2}
    bind:progress={progress2}
  >
    <div slot="background" class="image_container">
      <img src="/images/graphs/{recaudacionPeliculas[index2]}" alt="chart {index2}" class="charts"/>
    </div>
    <div slot="foreground" class="foreground_container">
      <section class="step_foreground">
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            Las películas de Tim Burton introdujeron al personaje a una audiencia más amplia que la de los cómics, 
            aumentando su popularidad globalmente.
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            La trilogía del Caballero de la Noche de Christopher Nolan compartió un enfoque más oscuro y profundo sobre el personaje.
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            Batman vs Superman, dirigida por Zack Snyder, enfrentó a dos héroes icónicos en un conflicto épico, 
            explorando temas de poder y responsabilidad.
          </p>
        </div>
      </section>
      <section class="step_foreground">
        <div class="epi_foreground">
          <p>
            Batman, dirigida por Matt Reeves, ofreció una interpretación centrada en las 
            habilidades detectivescas de Batman, continuando con la atmósfera oscura tan arraigada al personaje.
          </p>
        </div>
      </section>
    </div>
  </Scroller>

  <div class="scroll-section">
    <div class="scroll-container">
        <div class="scroll-content">
            <img src="/images/peliculas.png" alt="Imagen Ancha" class="ancha">
            <img src="/images/peliculas.png" alt="Imagen Ancha" class="ancha">
        </div>
    </div>
  </div>
  
  <div class="sección-nueva">
    <p style="font-style: italic;">
      La fama de Batman no solo proviene de sus exitosas películas, sino también de su poderosa presencia en el mundo del merchandising.
    </p>
    <p>
      Según Visual Capitalist, Batman ha generado aproximadamente $21.3 mil millones en ingresos por merchandising. 
      Esta cifra incluye una amplia gama de productos, desde juguetes y ropa hasta artículos de colección, lo que 
      subraya la influencia significativa del merchandising en la popularidad y el reconocimiento global del personaje.
    </p>
    <div class="image_container_in">
      <img src="/images/graphs/fuentes_recaudacion.png" alt="fuentes recaudacion"/>
    </div>
  </div>

  <div class="sección-nueva">
    <h2>Patrón del éxito: ¿qué hace a batman tan popular?</h2>
    <p>
      Dentro de los cómics más populares de Batman a lo largo de los años, los mejores puntuados por los fans 
      son “El Caballero de la Noche Regresa”, “Batman: La Broma Asesina”, “Batman: La Larga Halloween”. Por otro lado,
      la trilogía del Caballero de la Noche de Christopher Nolan fue la mejor recibida por el público.
    </p>
  </div>

  <div class="image_container_in">
    <img src="/images/graphs/rating_comics_pelis.png" alt="chart rating"/>
  </div>

  <div class="sección-nueva">
    <p>
      Además de la gran popularidad del director, no es 
      coincidencia que los temas y personajes que se tocan en dicha trilogía coincidan con los cómics historicamente 
      proclamados por la crítica. Lo que sugiere que uno de los grandes atractivos de Batman, no solo como personaje, 
      sino como ícono popular es el abanico de temas profundos, serios y oscuros que trata, ya sea en la relación 
      con otros personajes o en su código moral.
    </p>
  </div>

  <div class="linea">
    <section id="timeline">
      <ul>
        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2005</span>Batman Begins</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              Destaca por su exploración profunda de temas como el miedo, la justicia y la identidad.
              La película revitaliza el origen de Batman, mostrando la transformación de Bruce Wayne en el Caballero de la Noche.
              Se explora de manera detallada la lucha interna y motivaciones de Bruce Wayne. 
              Esta película coincide con la narrativa de cómics famosos como "Batman: Año Uno", "El hombre que cae" y "La Larga Halloween".
            </p>
            <button>Ver Cómics</button>
          </div>
        </li>

        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2008</span>The Dark Knight</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              Explora temas de caos, moralidad y dualidad. La película profundiza en la lucha de Batman contra el Guasón, 
              un agente del caos que desafía sus límites y principios. La relación entre Batman y 
              el Joker resalta la delgada línea entre el orden y la anarquía, coincidiendo con la 
              narrativa de cómics como "La Broma Asesina".
            </p>
            <button>Ver Cómics</button>
          </div>
        </li>
      
        <li class="blue-box">
          <i></i>
          <div class="box">
            <h3 class="title"><span class="year">2012</span>The Dark Knight Rises</h3>
            <p style="font-family: 'Comic Neue', sans-serif;">
              El Caballero de la Noche Asciende aborda temas de redención, sacrificio y resurgimiento. 
              La película muestra a Bruce Wayne enfrentando sus miedos y luchando por la salvación de Ciudad Gótica. 
              La presencia de Bane y Talia al Ghul conecta con la serie de cómics "La caída del caballero" y 
              "La tierra de nadie", destacando la perseverancia de Batman ante desafíos extremos.
            </p>
            <button>Ver Cómics</button>
          </div>
        </li>
      </ul>
    </section>
  </div>

  <div class="sección-nueva">
    <h2>El legado del Caballero de la Noche</h2>
    <p>
      Desde su debut en 1939, Batman se ha convertido en un ícono cultural, simbolizando justicia, determinación 
      y resiliencia. Con múltiples reinterpretaciones en cómics, series de televisión, y películas, ha influenciado 
      generaciones y ha reflejado cambios sociales y culturales. Su complejidad psicológica y su lucha contra 
      el crimen en una ciudad corrupta han resonado profundamente con el público, cementando su estatus como uno 
      de los superhéroes más emblemáticos de todos los tiempos.
    </p>
    <p style="margin-top: 5%; text-align: right; font-style: italic;"> "Muere siendo un héroe, o vive lo suficiente para verte convertido en el villano."</p>
    <p style="margin-bottom: 5%; text-align: right; font-style: italic;">-Batman</p>

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
        <img src="/images/iconos/facebook.svg" alt="Facebook">
        <img src="/images/iconos/twitter.svg" alt="Twitter">
        <img src="/images/iconos/whatsapp.svg" alt="Whatsapp">
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

  .dialogo-bruce{
    position: relative;
    width: 100%; 
    height: 700px; 
    margin-top: 4%;
  }

  .sección-nueva {
    padding: 20px;
    margin: 0 5%; /*270px seria como graf y timeline creo*/
    margin-top: 4vh;
    text-align: left;
}

  .sección-nueva h2 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 2em;
      margin-bottom: 10px;
      color: #ffcc00;  
  }

  .sección-nueva p {
      font-family: 'Comic Neue', sans-serif;
      font-size: 1.2em;
      line-height: 1.5;
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

  .text-image-container {
    position: relative;
    width: 100%;
    margin: 0 auto;
  }

  .text-overlay {
    
      position: absolute;
      top: 25%;
      left: 5%;
      width: 38%;
      z-index: 2;
      padding: 20px;
      border-radius: 10px;
  }

  .text-overlay p {
      margin: 0 0 10px;
      font-size: 1.2em;
      line-height: 1.5;
  }

  .image {
      width: 100%;
      display: block;
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
    height: 80vh;
  }
  .image_container img {
    width: 950px;
  }

  .container-lluvia {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background: #000;
  }

  .bat-im {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    pointer-events: none; /* Evitar que el canvas interfiera con eventos de ratón */
  }

  /* .bat-im{
    width: 100vw;
    height: 100vh;
    position: center;
  } */

  .scroll-section {
    margin-top: 5%;
    width: 100vw;
    overflow: hidden;
    display: flex;
    justify-content: center; /* Centra horizontalmente */
    align-items: center; /* Centra verticalmente */
  }

  .scroll-container {
      width: 100%;
      height: auto;
      overflow: hidden;
      white-space: nowrap;
  }

  .scroll-content {
      display: flex;
      animation: scroll-horizontal 20s linear infinite;
  }

  .ancha {
      height: 25vh; /* Ajusta la altura de la imagen según sea necesario */
      width: auto; /* Mantiene la proporción de la imagen */
  }

  @keyframes scroll-horizontal {
      0% {
          transform: translateX(0);
      }
      100% {
          transform: translateX(-50%); /* Mueve hasta la mitad del contenedor (una imagen completa) */
      }
  }
  
  .image_container_in { /* para los graficos que no son de algun scroll */
    display: flex;
    justify-content: center;
    align-items: center;
    height: 75vh;
  }
  .image_container_in img {
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
    font-size: 1rem;
    margin: 0 0.5rem;
  }

  #timeline p{
    padding-right: 1rem;
    padding-left: 1rem;
    padding-top: 0.8rem;
    color: #000;
  }

  #timeline button{
    border: 1px solid #ddd;
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
