<template>
  <div>
    <div
      class="is-flex has-background-link-dark is-flex-direction-row is-justify-content-space-between p-4 fixed"
    >
      <div class="p-1 px-3 is-flex is-align-items-center">
        <img src="@/assets/icon.png" />
        <span class="is-size-5 has-text-light pl-2 f-raleway is-bold">Nkamar</span>
      </div>

      <div class="p-1 px-3 is-flex is-align-items-center" id="menu">
        <span class="is-size-7 is-white pl-4 f-raleway nav-link is-bold "  @click="$router.push('/#ccm')"
          >Comment &ccedil;a marche ?</span
        >
        <span class="is-size-7 is-white pl-4 f-raleway nav-link is-bold "  @click="$router.push('/#cc')"
          >Contactez-nous</span
        >
        <span class="is-size-7 is-white pl-4 f-raleway nav-link is-bold "   @click="$router.push('/inscription')"
          >Inscription</span
        >
        <span class="is-size-7 is-white pl-4 f-raleway nav-link is-bold " @click="$router.push('/connexion')"
          >Connexion</span
        >
      </div>
      <div id="menu-hamburger" class="pt-1">
             <b-dropdown aria-role="list">
            <template #trigger="{ active }">
                <b-button
                    type="is-primary"
                    style="background-color: transparent"
                    :icon-right="active ? 'close' : 'menu'" />
            </template>


            <b-dropdown-item aria-role="listitem" id="go-ccm"  @click="$router.push('/#ccm')">
              <b-icon icon="frequently-asked-questions" class="pr-3"></b-icon>
              Comment &ccedil;a marche ?</b-dropdown-item>
            <hr class="dropdown-divider">
            <b-dropdown-item aria-role="listitem"  @click="$router.push('/#cc')" >
              <b-icon icon="gesture-tap-button" class="pr-3"></b-icon>
              Contactez-nous</b-dropdown-item>
            <hr class="dropdown-divider">
            <b-dropdown-item aria-role="listitem"  @click="$router.push('/inscription')">
              <b-icon icon="shield-account-outline" class="pr-3"></b-icon>
              Inscription</b-dropdown-item>
            <hr class="dropdown-divider">
            <b-dropdown-item aria-role="listitem"  @click="$router.push('/connexion')">
              <b-icon icon="account-key" class="pr-3"></b-icon>
              Connexion</b-dropdown-item>
        </b-dropdown>
      </div>
    </div>

    <div class="columns polygon-header has-background-link-dark h130 p-6 mt-6">
      <div class="column is-three-fifths has-text-light pt-6">
        <h1 class="is-size-6">Bienvenu,</h1>
        <b class="is-bold is-size-2 fs-medium"
          >Inscrivez-vous , parrainez vos proches pour generer des fonds chaque
          jour sans aucunes limites</b
        >
        <br />
        <button class="button border-none has-text-link-dark mt-6 is-rounded ">
          Commencez maintenant
        </button>
      </div>
    </div>

    <div class="fix-position px-5">
      <div class="columns is-centered">
        <div class="column is-four-fifths" id="ccm">
          <p class="is-bold is-size-5 is-dark pl-4 f-raleway">Comment ça marche ?</p>
          <!--  -->
          <div class="columns mt-6">
            <div class="column order">
              <login />
            </div>
            <div class="column centered-grid is-size-6">
              <div class="p-5">
                Creer votre compte dans la fenetre
                <nuxt-link class="m-0 p-0" to="/inscription">Inscription</nuxt-link>
                et ensuite valider votre compte .N’hésitez pas en fin de
                partager votre ID de parrainage / liens de parrainage!
              </div>
            </div>
          </div>
          <!--  -->

          <!--  -->
          <div class="columns">
            <div class="column order showit">
              <network />
            </div>
            <div class="column centered-grid is-size-6">
              <div class="p-5">
                Obtenez une rémunération brute de 4 à 80% sur vos parrainages.
                Un des services a utiliser au quotidien et qui me permet de
                gagner de l’argent de manière régulière.
              </div>
            </div>

            <div class="column order hidit">
              <network />
            </div>
          </div>
          <!--  -->

          <!--  -->
          <div class="columns mt-6">
            <div class="column order showit">
              <invest />
            </div>
            <div class="column centered-grid is-size-6">
              <div class="p-5">
                Rechargez votre solde selon la formule pour activer votre compte
                et commencez a faire votre premier parrainage
              </div>
            </div>
            <div class="column order hidit">
              <invest />
            </div>
          </div>
          <!--  -->

          <p class="is-bold is-size-5 is-dark pl-4 f-raleway mt-6 py-6">
            Contactez-nous
          </p>

          <div class="box mt-4 p-6" id="cc">
            <div class="columns">
              <div class="column">
                <b-field label-position="" label="Email">
                  <b-input icon="email"></b-input>
                </b-field>
              </div>

              <div class="column">
                <b-field label-position="" label="Telephone">
                  <b-input icon="phone"></b-input>
                </b-field>
              </div>
            </div>

            <div class="columns">
              <div class="column">
                <b-field label-position="" label="Message">
                  <b-input type="textarea"></b-input>
                </b-field>
              </div>
            </div>

            <div class="is-flex is-justify-content-end">
              <div class="">
                <b-button
                  type="is-link"
                  label="Envoyer"
                  rounded
                  icon-right="send"
                ></b-button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>


    <div class="polygon-footer h30-footer has-background-link-dark p-4 has-text-light pt-5">
      <p class="mt-6 pt-6 is-size-7">Copyright Nkamar@2022 v1.0.3</p>
    </div>
  </div>
</template>

<script>
import Network from "../components/network.vue";
import Login from "../components/login.vue";
import Invest from "../components/invest.vue";

if (process.client) {

  // open on click on button

  document.querySelector("#go-ccm").addEventListener("click", function () {
    document.querySelector("#ccm").scrollIntoView({
      behavior: "smooth", // Defines the transition animation. default: auto
      block: "nearest", // Defines vertical alignment. default: start
      inline: "nearest", // Defines horizontal alignment. default: nearest
    });
  });

  document.querySelector("#go-cc").addEventListener("click", function () {
    document.querySelector("#cc").scrollIntoView({
      behavior: "smooth", // Defines the transition animation. default: auto
      block: "nearest", // Defines vertical alignment. default: start
      inline: "nearest", // Defines horizontal alignment. default: nearest
    });
  });

} else {
  console.log('server process');
}
export default { components: { Network, Login, Invest } };
</script>

<style>

.open-menu {
    display: block !important;
  }
</style>
