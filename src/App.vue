<template>
  
    <div id="imageR">
      <div class="userImage">
        <nav>
          <p>@Code by Dms</p>
          <ul>
            <li>Work</li>
            <li>About</li>
            <li>Contact</li>
          </ul>
        </nav>
        
        <div class="info">
          <p><i class="fa-solid fa-laptop"></i><br><br><br>
            Freelance<br>
             Full Stack developer  </p>
             <div class="location">
                <dive class="text">Located <br>in <br>Algeria</dive>
                <div class="globe"><i class="fa-solid fa-globe"></i></div>
             </div>
          <div class="slider">
            <p class="text1 animate1">Damis <br> Med Ilias</p>
          </div>
        </div>
      </div>
    </div>
    <article id="man">
      <div >
      <p>I am Damis Mohamed Ilias, <span>Full Stack</span> developer specialized in front-end and back-end technologies
      
         Passionate about creating secure and user-friendly web applications, I have expertise in developing high-performance web applications.
        
        Holding a <span>bachelor's</span> degree in software engineering, I continually strive to expand my skills and knowledge.</p>
      </div>
      <a href="">More <i class="fa-regular fa-hand-point-left"></i></a>
    </article>
    <footer>
     
    </footer>
  </template>
  
  <script>
  export default {
    name: "MyComponent",
    data() {
      return {
        x : true ,
        currentId1: 'text1',
        currentId2: 'text2'
      };
    },
    mounted() {
      this.initializeVanta();
      this.startSwitchingElements();
      window.addEventListener('scroll', this.handleScroll);
    },
    methods: {
      initializeVanta() {
        /*VANTA.WAVES({
          el: "#man",
          mouseControls: true,
    touchControls: true,
    gyroControls: false,
    minHeight: 200.00,
    minWidth: 200.00,
    scale: 1.00,
    scaleMobile: 1.00,
    color: 0x999D9E,
    waveHeight: 11.00
        });*/
        VANTA.CELLS({
    el: "#man",
    mouseControls: true,
    touchControls: true,
    gyroControls: false,
    minHeight: 200.00,
    minWidth: 200.00,
    scale: 1.00,
    color2: 0x141517,
    color1: 0x1C1C10,
    size: 2.40,
    speed: 2.00
  })
      },
  
      switchElements() {
        const text1 = document.querySelector('.text1');
        const text2 = document.querySelector('.text2');
        
   
        if (text1 && text2 && text1.parentNode === text2.parentNode) {
          const parent = text1.parentNode;
          if(this.x == true){
          parent.insertBefore(text2, text1);
          }
          else{
            parent.insertBefore(text1, text2); 
          }
  
          this.x = !this.x
        }
  
      },
  
      startSwitchingElements() {
        setInterval(() => {
          this.switchElements();
        }, 15000);
      },
      handleScroll() {
        const scrollPosition = window.scrollY;
        const elements = document.querySelectorAll('.slider span');
  
        elements.forEach(element => {
          if (scrollPosition > 10) {
  
            if (element.classList.contains('animate1')) {
              element.classList.remove('animate1');
              element.classList.add('animate2');
            }
          } else {
            if (element.classList.contains('animate2')) {
              element.classList.remove('animate2');
              element.classList.add('animate1');
            }
          }
        });
      }
    }
  };
  </script>
  
  
  <style lang="scss">
  #imageR {
    width: 100%;
    height: 100vh;
    //background-image: url('/src/assets/dms3-r.png');
    background-position: 40%;
    background-size: 17%;
    background-repeat: repeat;
    background-color: #999D9E;
  
    .userImage {
      height: 100vh;
      background-image: url('/src/assets/photo23.png');
      background-position: 55% 65%;
      background-size: 53%;
      background-repeat: no-repeat;
    }
  }
  
  #man {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: clamp(1em, 1.9vw, 1.5em);
      font-weight: 400;
      font-style: normal;
      line-height: 1.4;
      color: white;
      
    div{
      box-sizing: border-box;
      padding: 40px 60px;
      width: 65%;
      height: 60%;
      z-index: 1;
      animation: view linear ;
        animation-timeline: scroll();
      span{
        font-weight: 550;
      }
    }
    a{
      padding: 5px 15px;
      color: red;
      z-index: 1;
      width: 130px;
      height: 25px;
      i{
         animation: view2 4s ease-out infinite;
      }
    }
  }
  
  nav {
    display: flex;
    justify-content: space-between;
    padding-inline: 25px;
    padding-top: 33px;
    color: #ffffff;
    ul {
      display: flex;
      width: 245px;
      justify-content: space-around;
      list-style: none;
    }
  }
  
  .info {
    box-sizing: border-box;
    display: grid;
    height: 100%;
    overflow: hidden;
    grid-template-areas:
      "name job"
      "x3 jo";
    grid-template-columns: 51% 49%;
    grid-template-rows:  auto 230px;
    padding-top: 50px;
  
    p:first-child {
      align-self: center;
      justify-self: flex-end;
      grid-area: job;
      font-size: clamp(1.55em, 2.2vw, 2.5em);
      font-weight: 450;
      font-style: normal;
      line-height: 1.4;
      color: white;
      padding-right:50px ;
    }
    .location {
      grid-area: x3;
      background-color: #141517;
      width: 237px;
      height: 95px;
      align-self: center;
      border-radius: 0px 60px 60px 0;
      margin-bottom: 30px;
      display: flex;
  
      .text{
        color: #ffffff;
        width: 55%;
        font-weight: 450;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      .globe{
        background-color: #999D9E;
        align-self: center;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 70px;
        height: 70px;
        border-radius: 50%;
        margin-left: 20px;
        i{
          font-size: 29px;
          color: #ffffff;
          animation: spin 7s ease-out infinite; 
        }
      }
      }
    .slider {
      grid-area: name;
      font-size: 73px;
      position: relative;
      display: flex;
      align-items: center;
      font-weight: 450;
      white-space: nowrap;
      width: 100%;
      overflow: hidden;
      animation: typing 10s linear infinite ;
      //padding-bottom: 125px;
      p{
        color:#ffffff
      }
    }
  
  .text1 , .text2{
    //padding-left: 100px;
      //white-space: nowrap;
  
    }
  }
  .animate1{
   // animation: slide 15s linear infinite ;
    }
    .text2.animate2{
      position: absolute;
      right: 100%;
      //animation: slide2 15s linear infinite ;
  
    }
    .animate2{
      right: 100%;
      //animation: slide2 15s linear infinite ;
    }
  @keyframes slide {
    0% {
      transform: translateX(0%);
    }
    100%{
      
      transform: translateX(-100%);
    }
  }
  @keyframes slide2 {
    0% {
      transform: translateX(0%);
    }
    100%{
      transform: translateX(100%);
    }
  }
  @keyframes spin {
    0% {
      transform: rotateX(0deg)
      rotateY(0deg);
    }
    50%{
      transform: 
      rotateY(180deg);
    }
    80%{
      transform:rotateY(-360deg)
       rotateX(-20deg);
    }
    100%{
      transform: rotateX(180deg);
    }
  }
  @keyframes view {
    0% {
      transform: translate(-350px);
      opacity: 0;
    }
    100%{
      transform: translate(0);
      opacity: 1;
    }
  }
  @keyframes view2 {
    0% {
      transform: translate(10px);
  
    }
    100%{
      transform: translate(0);
  
    }

  }

  @keyframes typing {
    0% {
      width: 0;
    }
    20%{
      width:0%
    }
    30%{
      width: 100%
    }
    90%{
      width: 100%
    }
    100%{
      width:0%
    }
    }
  </style>
  