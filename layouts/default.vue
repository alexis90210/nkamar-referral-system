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
@import url("https://fonts.googleapis.com/css2?family=Raleway:wght@800&display=swap");

* {
  transition: all 0.3s ease-in;
  box-sizing: border-box;
}

.f-raleway {
  font-family: "Raleway";
}
.sigin_in {
  width: 393px;
  height: 351.73152px;
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
  height: 130vh;
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

@media screen and (max-width: 740px) {
  .illustra {
    width: 80% !important;
    height: auto !important;
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

  .mobile {
    position: absolute;
    right: 0;
    top: 0;
    width: 50vw;
    flex-direction: column;
    justify-content: center;
    z-index: 1000;
    height: 100vh;
    background-color: rgb(255, 255, 255);
    display: none !important;
  }

  .mobile > * {
    color: rgb(89, 89, 188) !important;
    padding-top: 10px;
    padding-bottom: 10px;
    display: flex;
    justify-content: flex-start;
    width: 100%;
    font-size: 0.8em !important;
  }

  .h130 {
    height: 90vh;
    width: 106%;
  }

  .h30-footer {
    height: 30vh;
    width: 103%;
  }

  .fs-medium {
    font-size: 23px !important;
  }

  .open-menu {
    display: block !important;
  }

  .order {
    order: 1;
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
</style>
