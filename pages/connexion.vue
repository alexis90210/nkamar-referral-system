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
                Connexion
              </center>
              <Forgot/>
            </div>
            <div class="column is-two-fifths">
              <p class="is-size-5 is-dark pl-4 f-raleway mt-6 pt-6 pb-3 hidit is-bold">
                Bienvenu, Merci de vous Connecter
              </p>

              <div class="box mt-4 p-4 m-1">
                <div class="column">
                  <b-field label-position="" label="Login">
                    <b-input icon="account"></b-input>
                  </b-field>
                </div>

                <div class="column">
                  <b-field label-position="" label="Password">
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
                      @click="connexion"
                      label="Se connecter"
                      icon-right="send"
                    ></b-button>
                  </div>
                </div>
              </div>
              <center class="is-size-7 is-dark pl-4 f-raleway py-3 is-bold">
                Je n'ai pas encore de compte,
                <nuxt-link to="/inscription">S'inscrire ?</nuxt-link>
              </center>

              <div class="columns is-centered">
                <div class="column is-three-fifths">
                  <center class="is-size-7 is-dark pl-4 f-raleway py-3 is-bold">
                    Se connecter avec l'un de ces reseaux
                  </center>
                  <center class="columns is-centered">
                    <b-button
                      class="m-1"
                      icon-left="facebook"
                      type="is-info"
                    ></b-button>
                    <b-button
                      class="m-1"
                      icon-left="instagram"
                      type="is-danger"
                    ></b-button>
                    <b-button
                      class="m-1"
                      icon-left="google"
                      type="is-link"
                    ></b-button>
                  </center>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Forgot from '../components/forgot.vue';

export default {
  components: { Forgot },
  data(){
    return {
      user:{
        login:'',
        password:''
      },

    }
  },
  methods:{
    async connexion(){
      this.$router.push('/dashboard/069500886')
    }
  }
};
</script>

<style></style>
