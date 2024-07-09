<template>
  <div>
    <div  id="imageR">
      <div class="userImage">
    <nav>
      <p>code by dms</p>
      <ul>
        <li>projet</li>
        <li>information</li>
        <li>contact</li>
      </ul>
    </nav>
    <div class="info">
      <p>Freelance<br>developer</p>
      <p>Damis Med Ilias</p>
    </div>
    </div>
  </div>
    <article id="man">
      <p>hello i am dms ilias</p>
    </article>
    <footer></footer>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  mounted() {
    this.initializeVanta();
  },
  methods: {
    initializeVanta() {
      VANTA.WAVES({
        el: "#man",
        mouseControls: true,
        touchControls: false,
        gyroControls: false,
        minHeight: 200.00,
        minWidth: 200.00,
        scale: 1.00,
        scaleMobile: 1.00,
        color: 0x90909,
        shininess: 45.00,
        waveHeight: 4.00,
        waveSpeed: 0.20,
        zoom: 0.93
      })

  }
}
};
</script>

<style lang="scss">
#imageR{
  width: 100%;
  height: 100vh;
  color: aqua;
  background-image: url('/src/assets/dms2.jpg');
  background-position: 40%;
  background-size: 17%;
  background-repeat: repeat;

  .userImage{
    height: 100vh;
    background-image: url('/src/assets/dms2.jpg');
  background-position: 50%;
  background-size: 45%;
  background-repeat: no-repeat;
  backdrop-filter: blur(10px);
  } 
}
#man {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  p{
    color: white;
  }
}
</style>
