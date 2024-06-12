<script>
  import { onMount} from "svelte";
    
    let visible = false;

    onMount(() => {
      setTimeout(() => {
        visible = true;
      }, 5000); // 3000 ms = 3 segundos
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
    <img src="./public/images/batman-intro.png" alt="Presentacion Batman" class ="background">
    <img src="./public/images/batman-intro-dialogo.svg" alt="Presentacion Batman Dialogo" class = "overlay">
    
  </div>

  

  <div class="linea">
    <section id="timeline">
        <h2 class="heading">Timeline de los eventos</h2>
        <ul>
            <li class="yellow-box">
                <i></i>
                <div class="box">
                  <h3 class="title"><span class="year">1988</span>Asesinato de los Wayne</h3>
                  <p>
                    Los padres de Bruce Wayne son asesinados por un ladrón en un callejón. 
                    Este evento traumático da inicio a su obsesión con la justicia y la lucha contra el crimen en Gotham City.
                  </p>
                  <button>Ver Comics</button>
                </div>
            </li>

            <li class="yellow-box">
              <i></i>
              <div class="box">
                <h3 class="title"><span class="year">1996</span>Desaparición y entrenamiento</h3>
                <p>
                  Bruce Wayne viaja por el mundo, aprendiendo sobre la criminalidad. 
                  Es entrenado por Ra's al Ghul y Henri Ducard en la Liga de las Sombras, hasta
                  que Bruce se niega a ejecutar a un criminal por lo que decide destruir el templo de la Liga
                </p>
                <button>Ver Comics</button>
              </div>
          </li>

          <li class="yellow-box">
            <i></i>
            <div class="box">
              <h3 class="title"><span class="year">2004</span>Regreso a Gotham como Batman</h3>
              <p>
                Bruce regresa a Gotham y comienza a desarrollar su equipo de Batman.
                Aparece como Batman por primera vez interrumpiendo un envío de drogas de Carmine Falcone. Posteriormente, se enfreta
                al Espantapájaros y a Ra's al Ghul. Finalmente, una carta del Joker sugiere la llegada de un nuevo villano a Gotham.
              </p>
              <button>Ver Comics</button>
            </div>
          </li>

          <li class="blue-box">
            <i></i>
            <div class="box">
              <h3 class="title"><span class="year">2006</span>Aparicón del Joker</h3>
              <p>
                El Joker comienza una serie de robos y actos de terrorismo en Gotham, 
                desafiando la autoridad de la mafia y la policía. Batman se alía al fiscal de distrito Harvey Dent.
                El Joker amenaza con matar a personas cada día hasta que Batman revele su identidad. 
                Harvey Dent se declara como Batman para proteger a Bruce.
              </p>
              <button>Ver Comics</button>
            </div>
          </li>

          <li class="blue-box">
            <i></i>
            <div class="box">
              <h3 class="title"><span class="year">2007</span>Lucha contra Joker y Dos Caras</h3>
              <p>
                  Explosivos del Joker matan a Rachel Dawes y dejan a Harvey desfigurado. Se convierte en Dos Caras 
                  y comienza una vendetta personal contra aquellos que considera responsables de la muerte de Rachel.
                  Batman captura al Joker y enfrenta a Dos Caras, resultando en la muerte de éste último.
                  Batman asume la culpa de los crímenes de Dos Caras y se convierte en un fugitivo.
              </p>
              <button>Ver Comics</button>
            </div>
          </li>

          <li class="gray-box">
            <i></i>
            <div class="box">
              <h3 class="title"><span class="year">2015</span>Lucha contra Bane</h3>
              <p>
                Gotham ha disfrutado de una relativa paz gracias a la Ley Dent de tolerancia cero a los criminales, y Bruce Wayne
                se mantiene oculto en su mansión. Bane aparece en Gotham, llevando a cabo una serie de ataques y liberando a los prisioneros de Blackgate.
                Batman regresa y tiene su primera confrontación con Bane, resultando gravemente malherido. Tras su recuperación, Batman, derrota a Bane y salva
                a Gotham de una explosión nuclear pero a costa de su propia vida.
              </p>
              <button>Ver Comics</button>
            </div>
          </li>

          <li class="gray-box">
            <i></i>
            <div class="box">
              <h3 class="title"><span class="year">2016</span>Bruce encuentra la paz</h3>
              <p>
                Bruce, con Batman supuestamente muerto, deja a Gotham y se retira a una vida tranquila 
                y anónima en Italia junto con Selina Kyle, Catwoman.
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
    z-index: 1;
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

  #timeline ul li.yellow-box .box .title {
    background-color: #BC823A;
  }
  #timeline ul li.blue-box .box .title{
    background-color: #195664;
  }
  #timeline ul li.gray-box .box .title{
      background-color: #86959C;
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
    color: #2c3e50;
    font-size: 0.9rem;
    margin: 0 0.5rem;
  }

  #timeline p{
    padding-right: 1rem;
    padding-left: 1rem;
    color: #000;
    text-align: justify;
  }

  #timeline button{
    margin: 0.5rem 0rem 1rem 1rem;
    outline: none;
    border: 1px solid #ddd;
    padding: 0.5rem 1rem;
    border-radius: 50px;
    background: transparent;
    transition: all 0.3s ease-in;
    font-family: inherit;
    cursor: pointer;
  }

  #timeline button:hover{
    background-color: #E23720;
    color: #fff;
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
    background-color: #1F4389;
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
    background: #2c3e50;
    transform: translateX(-50%);
    border-radius: 50%;
  }

  #timeline ul li.yellow-box i {
    background-color: #E6D1A4;
  }
       
  #timeline ul li.blue-box i {
      background-color: #C0E5E5; 
  }

  #timeline ul li.gray-box i {
      background-color: #E1E5E4; 
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

  #timeline ul li.yellow-box:nth-child(odd) .box:before {
      left: -15px;
      border-width: 8px 16px 8px 0;
      border-color: transparent #BC823A transparent transparent;
  }
  #timeline ul li.yellow-box:nth-child(even) .box:before {
      right: -15px;
      border-width: 8px 0 8px 16px;
      border-color: transparent transparent transparent #BC823A;
  }

  #timeline ul li.blue-box:nth-child(odd) .box:before {
      left: -15px;
      border-width: 8px 16px 8px 0;
      border-color: transparent #195664 transparent transparent;
  }
  #timeline ul li.blue-box:nth-child(even) .box:before {
      right: -15px;
      border-width: 8px 0 8px 16px;
      border-color: transparent transparent transparent #195664;
  }

  #timeline ul li.gray-box:nth-child(odd) .box:before {
      left: -15px;
      border-width: 8px 16px 8px 0;
      border-color: transparent #86959C transparent transparent;
  }
  #timeline ul li.gray-box:nth-child(even) .box:before {
      right: -15px;
      border-width: 8px 0 8px 16px;
      border-color: transparent transparent transparent #86959C;
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
