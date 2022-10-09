<template>
  <div class="has-background-light" style="height: 130vh">
    <!-- loader -->
    <b-loading v-model="isLoadingFull" is-full-page></b-loading>

    <!-- starting view -->

    <div class="centered-grid py-6 has-background-light">
      <div
        class="columns has-background-light is-centered"
        style="position: absolute; z-index: 100; top: 0; left: 0; width: 100%"
      >
        <div class="column is-four-fifths">
          <div class="columns">
            <div class="column centered-grid">
              <center
                class="is-size-5 is-dark pl-4 f-raleway mt-6 showit is-bold"
              >
                <img
                  src="@/assets/icon.png"
                  class="showit my-3"
                  style="zoom: 160%"
                />
                Bienvenu, Merci de vous inscrire
                <Sigin_in class="hidit" />
              </center>
              <Sigin_in class="hidit" />
            </div>
            <div class="column is-two-fifths">
              <p
                class="is-size-5 is-dark pl-4 f-raleway mt-6 pt-6 pb-3 hidit is-bold"
              >
                Bienvenu, Merci de vous inscrire
              </p>

              <div class="box mt-4 p-4 m-1 ml-5">
                <div class="column">
                  <b-field
                    label-position=""
                    label="Mobile"
                    :type="
                      start_editing_mobile && user.mobile_filleul.length != 9
                        ? 'is-danger'
                        : user.mobile_filleul.length == 9
                        ? 'is-success'
                        : ''
                    "
                    :message="
                      start_editing_mobile && user.mobile_filleul.length != 9
                        ? 'Mobile incorrect'
                        : user.mobile_filleul.length == 9
                        ? 'Mobile correct'
                        : ''
                    "
                  >
                    <div class="is-flex">
                      <b-select icon="earth" v-model="user.code_mobile_filleul">
                        <option value="242">+242</option>
                      </b-select>

                      <b-input
                        class="ml-1"
                        type="tel"
                        v-model="user.mobile_filleul"
                        @input="start_editing_mobile = true"
                      ></b-input>
                    </div>
                  </b-field>
                </div>

                <div class="column">
                  <b-field
                    label-position=""
                    label="Password"
                    :type="
                      start_editing_password && user.password.length < 8
                        ? 'is-danger'
                        : user.password.length >= 8
                        ? 'is-success'
                        : ''
                    "
                    :message="
                      start_editing_password && user.password.length < 8
                        ? 'Taille minimale 8 caracteres'
                        : user.password.length >= 8
                        ? 'Password securisé'
                        : ''
                    "
                  >
                    <b-input
                      icon="lock"
                      @input="start_editing_password = true"
                      v-model="user.password"
                    ></b-input>
                  </b-field>
                </div>

                <div class="column">
                  <b-field
                    label-position=""
                    label="Confirmez votre Password"
                    :type="
                      start_editing_other_password &&
                      user.other_password != user.password
                        ? 'is-danger'
                        : user.other_password.length >= 8
                        ? 'is-success'
                        : ''
                    "
                    :message="
                      start_editing_other_password &&
                      user.other_password != user.password
                        ? 'Les deux mots de passe ne correspondent pas'
                        : user.other_password.length >= 8
                        ? 'Password confirmé'
                        : ''
                    "
                  >
                    <b-input
                      icon="lock"
                      v-model="user.other_password"
                      @input="start_editing_other_password = true"
                    ></b-input>
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
                      @click="inscription_step_1"
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

    <!-- MODAL -->
    <div class="modal is-active" v-if="start_inscription" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="box mx-3">
          <div class="media">
            <div class="media-left">
              <figure class="image is-48x48">
                <b-icon icon="account-circle" size="is-large"></b-icon>
              </figure>
            </div>
            <div class="media-content">
              <p class="title is-4 fs-medium">
                +{{ user.code_mobile_filleul }} {{ user.mobile_filleul }}
              </p>
              <p class="subtitle is-6">@{{ user.mobile_filleul }}</p>
            </div>
          </div>
          <div class="content py-3">
            Votre inscription est bientot terminee, veuillez indiquez votre
            parrain
            <br />

            <div class="columns">
              <div class="column mt-4">
                <b-field
                  label-position=""
                  label="Identifiant du parrain"
                  :type="
                    start_editing_identifiant_parrain &&
                    user.identifiant_parrain.length < 10
                      ? 'is-danger'
                      : user.identifiant_parrain.length >= 10
                      ? 'is-success'
                      : ''
                  "
                  :message="
                    start_editing_identifiant_parrain &&
                    user.identifiant_parrain.length < 10
                      ? 'Identifiant incorrect'
                      : user.identifiant_parrain.length >= 10
                      ? 'Identifiant correct'
                      : ''
                  "
                >
                  <div class="is-flex">
                    <b-input
                      class="ml-1"
                      type="tel"
                      v-model="user.identifiant_parrain"
                      @input="start_editing_identifiant_parrain = true"
                    ></b-input>
                  </div>
                </b-field>
              </div>
            </div>

            <b-button
              type="is-link"
              rounded
              @click="inscription_2"
              label="Suivant"
              icon-right="send"
            ></b-button>
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
  data() {
    return {
      user: {
        code_mobile_filleul: "242",
        mobile_filleul: "",
        identifiant_parrain: "",
        password: "",
        other_password: "",
      },
      start_editing_mobile: false,
      start_editing_password: false,
      start_editing_other_password: false,
      start_editing_identifiant_parrain: false,
      start_inscription: false,
      isLoadingFull: false,
    };
  },
  methods: {
    inscription_step_1() {
      if (this.user.mobile_filleul.length != 9) {
        return;
      }

      if (this.user.password.length < 8) {
        return;
      }

      if (this.user.password.length < 8) {
        return;
      }

      if (this.user.password != this.user.other_password) {
        return;
      }

      if (this.$route.query.referral && this.$route.query.referral.length > 9) {
        this.$router.push("/connexion");
      } else {
        this.start_inscription = true;
      }
    },

    inscription_2() {
      this.start_inscription = false;
      this.isLoadingFull = true;
    },
  },
};
</script>

<style></style>
