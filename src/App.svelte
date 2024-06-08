<script>

</script>

<body>
  <header>
    <h1>DataGeek</h1>
  </header>
  <main>
    <div id="batman-container">
      <div id="brave"></div>
    </div>
    <div class="ni-idea">
      <section id="timeline">
          <h2 class="heading">Responsive Timeline</h2>
          <ul>
              <li>
                  <i></i>
                  <div class="box">
                    <h3 class="title"><span class="year">2013</span>HTML Language</h3>
                    <p>
                        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo
                        possimus in ipsum iure eaque atque esse commodi molestiae, et odio!
                    </p>
                    <button>Read More</button>
                  </div>
              </li>
  
              <li>
                <i></i>
                <div class="box">
                  <h3 class="title"><span class="year">2014</span>HTML Language</h3>
                  <p>
                      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo
                      possimus in ipsum iure eaque atque esse commodi molestiae, et odio!
                  </p>
                  <button>Read More</button>
                </div>
            </li>
          </ul>
      </section>
    </div>
  </main>
  
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
      <p style="font-size: 10px; color:gray; margin-right:30px; margin-left:30px;">At our company, we are committed to ensuring the best personalized experience for the enjoyment of multimedia content. We deeply appreciate your trust in our service. Rest assured, we prioritize the protection of your data, ensuring that it remains private and secure. Your privacy is of utmost importance to us as we strive to provide a seamless and enriching entertainment experience tailored to your preferences.</p>
      <p style="color: gray" class="copyright">&copy; 2024 DataGeek</p>
    </div>
  </footer>
</body>



<style>

  body {
      margin: 0;
      padding: 0;
      background: #000;
      color: #fff;
      overflow-x: hidden;
    }

  header {
    background: #141414;
    color: #fff;
    text-align: center;
    position: fixed;
    top: 0;
    width: 100vw;
    height: 10vh;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
  }

  #batman-container {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
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
      background: #e0dfcd;
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
      100% { transform: translate(0%, -5%); } /* Mueve el elemento al centro del #brave */
  }

  #timeline .title {
    box-shadow: 10px 5px 10px rgba(0, 0, 0, 0.5);
    padding: 1rem 0rem 1rem 0.7rem;
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    color: #fff;
    font-size: 1.3rem;
    background-color: #3134de;
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
    padding: 1rem 0 1rem 1rem;
    color: #000;
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
    background-color: #17202a;
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
    background-color: #586bd6;
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

  #timeline ul li i{
    position: absolute;
    left: 50%;
    top: 20%;
    width: 45px;
    height: 45px;
    background: #2c3e50;
    transform: translateX(-50%);
    border-radius: 50%;
  }

  /*pico*/
  #timeline .box:before {
    content: "";
    position: absolute;
    top: 5px;
    width: 0;
    height: 0;
    border-style: solid;
  }
  #timeline ul li:nth-child(odd) .box:before {
    left: -15px;
    border-width: 8px 16px 8px 0;
    border-color: transparent #3134de transparent transparent;
  }
  #timeline ul li:nth-child(even) .box:before {
    right: -15px;
    border-width: 8px 0 8px 16px;
    border-color: transparent transparent transparent #3134de;
  }

  footer {
    background-color: rgba(14, 14, 14, 0.545);
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.7); 
    margin-top: 50px;
  }
  .footer-content {
    color: white;
    padding-top: 20px;
    text-align: center;
    font-family: 'Helvetica';
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
