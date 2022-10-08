<template>
    <div class="has-background-light" style="height: 130vh">
      <div class="centered-grid py-6 has-background-light">
        <div
          class="columns has-background-light is-centered"
          style="position: absolute; z-index: 100; top: 0; left: 0; width: 100%"
        >
          <div class="column is-four-fifths">
            <div class="columns">
              <div class="column centered-grid">
                <center class="is-size-5 is-dark pl-4 f-raleway mt-6 showit is-bold">
                  Inscription
                </center>
                <Sigin_in />
              </div>
              <div class="column is-two-fifths">
                <p class="is-size-5 is-dark pl-4 f-raleway mt-6 pt-6 pb-3 hidit is-bold">
                  Bienvenu, Merci de vous inscrire
                </p>
  
                <div class="box mt-4 p-4 m-1">
                  <div class="column">
                    <b-field label-position="" label="Mobile">
                      <b-input icon="account"></b-input>
                    </b-field>
                  </div>
  
                  <div class="column">
                    <b-field label-position="" label="Password">
                      <b-input icon="lock"></b-input>
                    </b-field>
                  </div>

                  <div class="column">
                    <b-field label-position="" label="Confirmez votre Password">
                      <b-input icon="lock"></b-input>
                    </b-field>
                  </div>
  
                  <div
                    class="is-flex is-justify-content-space-between pr-4 pt-3"
                    style="zoom: 80%"
                  >
                    <div>
                      <b-button
                        @click="$router.push('/')"
                        type="is-light"
                        label="Retour"
                        rounded
                        icon-right="keyboard-return"
                      ></b-button>
                    </div>
                    <div class="">
                      <b-button
                        type="is-link"
                        rounded
                        label="S'inscrire"
                        icon-right="send"
                      ></b-button>
                    </div>
                  </div>
                </div>
                <center class="is-size-7 is-dark pl-4 f-raleway py-3 is-bold">
                  J'ai deja un compte,
                  <nuxt-link to="/connexion">Se connecter ?</nuxt-link>
                </center>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import Sigin_in from "../components/sigin_in.vue";
  export default {
    components: { Sigin_in },
  };
  </script>
  
  <style></style>
  