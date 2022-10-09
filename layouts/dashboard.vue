<template>
  <div class="has-background-light ">
    <nav id="menu-dash" class="is-flex is-flex-direction-row is-justify-content-space-between p-1 is-align-items-center p-3">
      <div class="is-flex is-flex-direction-row is-justify-content-start is-align-items-center">
        <img src="@/assets/icon.png" class="zoomit" />
        <span class="is-size-5 pl-3 is-bold">Nkamar</span>
      </div>

      <div>
        <b-dropdown
            v-model="navigation"
            position="is-bottom-left"
            append-to-body
            aria-role="menu"
          >
            <template #trigger>
              <a class="navbar-item is-flex is-flex-direction-row is-justify-content-start is-align-items-center" 
              role="button">
                <span class="fs-medium pr-3 has-text-dark">@_{{role}}</span>
                <img src="@/assets/photo.png" style="border-radius:50%" />
                <!-- <b-icon icon="menu-down"></b-icon> -->
              </a>
            </template>

            <b-dropdown-item custom aria-role="menuitem">
              Connecte comme <b>Alexis ngoyi</b>
            </b-dropdown-item>
            <hr class="dropdown-divider" />
            <b-dropdown-item value="blog" aria-role="menuitem" @click="$router.push('/dashboard/'+role+'/profile')">
              <b-icon
                icon="account-tie-outline"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover"> Profile</span>
            </b-dropdown-item>

            <b-dropdown-item value="home" aria-role="menuitem"  @click="$router.push('/dashboard/'+role)">
              <b-icon
                icon="card-account-details"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover"> Tableau de bord</span>
            </b-dropdown-item>
            <b-dropdown-item value="products" aria-role="menuitem" @click="$router.push('/dashboard/'+role+'/mes-revenus')">
              <b-icon
                icon="account-cash-outline"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover"> Mes Revenus</span>
            </b-dropdown-item>

            <b-dropdown-item value="products" aria-role="menuitem"  @click="$router.push('/dashboard/'+role+'/historique-retrait')">
              <b-icon
                icon="cash-refund"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover">Historique Retrait</span>
            </b-dropdown-item>

            <hr class="dropdown-divider" aria-role="menuitem" />
            <b-dropdown-item value="Parainages"  @click="$router.push('/dashboard/'+role+'/mes-parrainnages')">
              <b-icon
                icon="account-details-outline"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover">Mes parrainages</span>
            </b-dropdown-item>

            <b-dropdown-item value="notification"   @click="$router.push('/dashboard/'+role + '/notifications')">
            <b-icon
              icon="message-alert-outline"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover"> Notifications</span></b-dropdown-item>
            <hr class="dropdown-divider" />
            <b-dropdown-item value="logout" aria-role="menuitem" @click="$router.push('/')">
              <b-icon icon="logout"></b-icon>
              Deconnexion
            </b-dropdown-item>
          </b-dropdown>
        
      </div>
    </nav>

    <div class="columns">
      <div class="column pl-6 hidit">
        <p class="menu-label mt-6">PROFILE</p>
        <ul class="menu-list">
          
          <li class="p-1 py-2" @click="$router.push('/dashboard/'+role+'/profile')">
            <b-icon
              icon="account-tie-outline"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover"> Profile</span>
          </li>
          <li class="p-1 py-2"  @click="$router.push('/dashboard/'+role)">
            <b-icon
              icon="card-account-details"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover"> Tableau de bord</span>
          </li>
          <li class="p-1 py-2" @click="$router.push('/dashboard/'+role+'/mes-revenus')">
            <b-icon
              icon="account-cash-outline"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover"> Mes Revenus</span>
          </li>
          <li class="p-1 py-2" @click="$router.push('/dashboard/'+role+'/historique-retrait')">
            <b-icon
                icon="cash-refund"
                size="is-small"
                class="pr-3"
              ></b-icon
              ><span class="fs-medium nav-hover">Historique Retrait</span>
          </li>
          <li class="p-1 py-2" @click="$router.push('/dashboard/'+role+'/mes-parrainnages')">
            <b-icon
              icon="account-details-outline"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover">Mes parrainages</span>
          </li>

          <li class="p-1 py-2"  @click="$router.push('/dashboard/'+role + '/notifications')">
            <b-icon
              icon="message-alert-outline"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover"> Notifications</span>
          </li>

          <li class="p-1 py-2" @click="$router.push('/')">
            <b-icon
              icon="logout"
              size="is-small"
              class="pr-3"
            ></b-icon
            ><span class="fs-medium nav-hover">Deconnexion</span>
          </li>
        </ul>
      </div>

      <div class="column is-four-fifths">      
        <div class="">
          <nuxt />
        </div>
        <center>
          <p class="menu-label my-6 is-bold is-size-7">Nkamar copyright @2022</p>
        </center>
      </div>
    </div>
  </div>
</template>

<script>

if(process.client) {
  addEventListener('scroll', (event) => {
    if(window.scrollY > 30) {
      document.querySelector("#menu-dash").classList.add('fixed-menu')
    } else {
      document.querySelector("#menu-dash").classList.remove('fixed-menu')
    }
  });

}
export default {
  data() {
    return {
      navigation: 'home',
      role:'069500765'
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:wght@800&display=swap");
.modal-background {
  background-color: rgba(10, 10, 10, 0.322);
}
.go-right {
  width: 100%;
  font-size: 14px;
  text-align: right;
  padding: 4px;
}

.th-wrap > .is-relative {
    font-weight: bold;
    font-size: 12px;
}

.menu-list > li {
  cursor: pointer;
}

.nav-hover:hover {
  text-decoration: underline;
}

* {
  transition: all 0.3s ease-in;
  box-sizing: border-box;
  font-family: "Ubuntu" !important;
  scroll-behavior: smooth;
}

.zoomit {
  zoom: 100%
}

.fixed-menu {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 300;
  width: 100%;
  transition: all .2s ease-in !important;
  background-color: rgba(255, 255, 255, 1);
  box-shadow: 0px 10px 15px -3px rgba(0,0,0,0.1);
}

.fixed{
  width:100%;
  position: absolute;
  z-index: 90;
  top:0;
  left:0;
  transition:all 1.3s ease-in
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


.cs::-webkit-scrollbar {
  width: 7px;
  height: 7px;
}
.cs::-webkit-scrollbar-button {
  width: 0px;
  height: 0px;
}
.cs::-webkit-scrollbar-thumb {
  background: #e1e1e1;
  border: 0px none #ffffff;
  border-radius: 50px;
}
.cs::-webkit-scrollbar-thumb:hover {
  background: #ffffff;
}
.cs::-webkit-scrollbar-thumb:active {
  background: #5e4eb1;
}
.cs::-webkit-scrollbar-track {
  background: #ffffff;
  border: 0px none #ffffff;
  border-radius: 50px;
}
.cs::-webkit-scrollbar-track:hover {
  background: #d1cccc;
}
.cs::-webkit-scrollbar-track:active {
  background: #ffffff;
}
.cs::-webkit-scrollbar-corner {
  background: transparent;
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
    padding: 15px;
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
@media screen and (min-width: 394px) and (max-width: 420px) {
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
    padding: 15px;
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
    padding: 5px;
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
    padding: 5px;
    /* text-align: center; */
  }
}

@media screen and (max-height: 640px) {
  .h130 {
    height: 150vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }
}

@media screen and (min-height: 640px) and (max-width: 350px) {
  .h130 {
    height: 70vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }
}

@media screen and (min-height: 800px) and (max-width: 420px) {
  .h130 {
    height: 70vh;
    width: 106%;
  }

  .fs-welcome {
    font-size: 13px !important;
    padding-bottom: 10px;
  }
}

@media screen and (min-height: 1000px) and (max-width: 830px) {
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

@media screen and (min-height: 1200px) and (min-width: 900px) {
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
