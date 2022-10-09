<template>
  <div>
    <nuxt />
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@800&display=swap');
.modal-background {
    background-color: rgba(10, 10, 10, 0.322);
}
* {
  transition: all 0.3s ease-in;
  box-sizing: border-box;
  font-family: 'Ubuntu', sans-serif !important;
  scroll-behavior: smooth;
}

.sigin_in {
  width: 393px;
  height: 351.73152px;
}

.is-bold {
  font-weight: 700;
}

.nav-link:hover {
  color: #ffcc00 !important;
  cursor: pointer;
}

.fixed {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 300;
  width: 100%;
}

.bg-yellow {
  background-color: #ffcc00 !important;
}

.polygon-header {
  clip-path: polygon(0 0, 100% 0, 100% 50%, 0 70%);
}

.polygon-footer {
  clip-path: polygon(0 0%, 100% 100%, 100% 100%, 0% 100%);
}

.h130 {
  height: 65vh;
  width: 110%;
}
.h30-footer {
  height: 30vh;
  width: 110%;
}
.border-none {
  border: none;
}

.is-white {
  color: white;
}

#menu-hamburger {
  display: none;
}

.fix-position {
  position: relative;
  top: -200px;
  z-index: 100;
}

.centered-grid {
  display: grid;
  align-items: center;
  justify-content: center;
}

.illustra {
  width: 506.63176px;
  height: 300.76576px;
}

.showit {
  display: none;
}

.field > .label {
  font-size: 13px;
}

/* Width 740px */

@media screen and (max-width: 740px) {
  .illustra {
    width: 50% !important;
    height: auto !important;
    margin-top: 30px;
    margin-bottom: 30px;
    
  }

  .fs-demo-text {
    font-size: 25px !important;
    margin-top: 30px;
    margin-bottom: 30px;
    padding:15px;
    text-align: center;
  }

  .fix-position {
    position: relative;
    top: -200px;
    z-index: 100;
  }

  #menu {
    display: none !important;
  }

  #menu-hamburger {
    display: block !important;
  }


  .h130 {
    /* height: 90vh; */
    width: 106%;
  }



  .fs-medium {
    font-size: 30px !important;
  }

  .fs-welcome {
    font-size: 22px !important;
    padding-bottom: 20px;
  }



  .hidit {
    display: none;
  }

  .showit {
    display: block !important;
  }

  .sigin_in {
    width: 193px;
    height: 251.73152px;
  }
}


/*  width 420px */
@media screen and (min-width:394px ) and (max-width: 420px) {

.h130 {
    height: 115vh;
    width: 106%;
  }
  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

  .fs-medium {
    font-size: 20px !important;
  }

  .fs-demo-text {
    font-size: 18px !important;
    margin-top: 20px;
    margin-bottom: 20px;
    padding:15px;
    /* text-align: center; */
  }
}

/*  width 322px and 394px */
@media screen and (min-width: 322px) and (max-width: 394px) {
  .h130 {
    height: 85vh;
    width: 106%;
  }

  .fs-medium {
    font-size: 16px !important;
  }

  .fs-demo-text {
    font-size: 14px !important;
    margin-top: 5px;
    margin-bottom: 5px;
    padding:5px;
    /* text-align: center; */
  }
}

/*  width 320px */
@media screen and (max-width: 320px) {
  .h130 {
    height: 118vh;
    width: 106%;
  }
  .fs-medium {
    font-size: 18px !important;
  }

  .fs-demo-text {
    font-size: 15px !important;
    margin-top: 10px;
    margin-bottom: 10px;
    padding:5px;
    /* text-align: center; */
  }

}

@media screen and  (max-height: 640px) {
  .h130 {
    height: 150vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

}

@media screen and  (min-height: 640px) and (max-width:350px) {
  .h130 {
    height: 70vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

}

@media screen and  (min-height: 800px) and (max-width:420px) {
  .h130 {
    height: 70vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

}


@media screen and  (min-height: 1000px) and (max-width:830px) {
  .h130 {
    height: 80vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

  .illustra {
    width: 70% !important;
    height: auto !important;
    margin-top: 30px;
    margin-bottom: 30px;
    
  }

}

@media screen and  (min-height: 1200px) and (min-width:900px) {
  .h130 {
    height: 80vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }

  .illustra {
    width: 70% !important;
    height: auto !important;
    margin-top: 30px;
    margin-bottom: 30px;
    
  }

}
</style>
