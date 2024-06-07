<script>
 
</script>

<main>
  <div id="fullscreen-container"> 
    <div id="brave"></div>
  </div>
  <div class="ni idea">
    <h1> Timeline </h1>
    <section id="timeline">
        <h2 class="heading">Responsive Timeline</h2>
        <ul>
            <li>
                <i class="fa-brands fa-html5"></i>
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
              <i class="fa-brands fa-html5"></i>
              <div class="box">
                <h3 class="title"><span class="year">2014</span>HTML Language</h3>
                <p>
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo
                    possimus in ipsum iure eaque atque esse commodi molestiae, et odio!
                </p>
                <button>Read More</button>
              </div>
          </li>
          
          <li>
            <i class="fa-brands fa-html5"></i>
            <div class="box">
              <h3 class="title"><span class="year">2015</span>HTML Language</h3>
              <p>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo
                  possimus in ipsum iure eaque atque esse commodi molestiae, et odio!
              </p>
              <button>Read More</button>
            </div>
          </li>
          <li>
            <i class="fa-brands fa-html5"></i>
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


<style>
  #fullscreen-container {
    width: 100vw;
    height: 100vh;
    background: #000; 
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


  #timeline ul {
    padding: 50px 0;
  }

  #timeline ul li {
    list-style: none;
    position: relative;
    width: 7px;
    margin: 0 auto;
    padding-top: 50px;
    background-color: #58d68e;
  }

  #timeline ul li .box {
    position: relative;
    bottom: 0;
    width: 450px;
    background-color: #fff;
    box-shadow: 0 0 5px rgba(0,0,0,0.5);
    border-radius: 5px;
  }
</style>
