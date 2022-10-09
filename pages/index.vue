<template>
  <div class="has-background-white" style="zoom: 90%">
    <nav class="navbar py-4">
      <div class="container is-fluid">
        <div class="navbar-brand">
          <a class="navbar-item" href="/">
            <div class="p-1 px-3 is-flex is-align-items-center">
              <img src="@/assets/icon.png" />
              <span class="is-size-5 has-text-dark pl-2 f-raleway is-bold"
                >Nkamar</span
              >
            </div>
          </a>
          <a
            class="navbar-burger"
            role="button"
            @click="open=!open"
            aria-label="menu"
            aria-expanded="false"
          >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>
        <div class="navbar-menu">
          <div class="navbar-end">
            <a class="navbar-item" href="#a-propos">A-propos</a
            ><a class="navbar-item" href="#nous-contacter">Nous contacter</a
            ><a class="navbar-item" @click="$router.push('/inscription')"
              >Inscription</a
            ><a class="navbar-item" @click="$router.push('/connexion')"
              >Connexion</a
            >
          </div>
        </div>
      </div>
    </nav>
    <div class="navbar-item" v-if="open">
            <a class="navbar-item" href="#a-propos">A-propos</a
            ><a class="navbar-item" href="#nous-contacter">Nous contacter</a
            ><a class="navbar-item" @click="$router.push('/inscription')"
              >Inscription</a
            ><a class="navbar-item" @click="$router.push('/connexion')"
              >Connexion</a
            >
          </div>

    <div class="container is-fluid p-0">
      <div class="columns has-background-link has-text-light">
      <div class="column">
        <div class="my-6 pb-3 columns is-multiline">
          <div class="column is-12 is-6-desktop mx-auto has-text-centered">
            <h2 class="mb-4 is-size-1 is-size-3-mobile has-text-weight-bold">
              Bienvenu, cher visiteur
            </h2>
            <p class="subtitle has-text-light mb-5">
              <b class="is-bold"
                >Inscrivez-vous , parrainez vos proches pour generer des fonds
                chaque jour sans aucunes limites</b
              >
            </p>
          </div>
        </div>
      </div>
    </div>
    </div>

    <section class="section">
      <div class="container">
        <div
          class="columns is-multiline p-4 mt-5"
          id="a-propos"
          style="zoom: 80%"
        >
          <div class="column is-12 is-4-desktop">
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">
                  Travaillez a la maison
                </h4>
                <p class="subtitle has-text-dark">
                  Parrainnez depuis chez vous et gagnez votre commission
                </p>
              </div>
            </div>
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">
                  Investissement sur
                </h4>
                <p class="subtitle has-text-dark">
                  Votre Investissement ne sera jamais perdu, nous vous
                  garantissons un 100% gain
                </p>
              </div>
            </div>
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">
                  Retrait d'argent
                </h4>
                <p class="subtitle has-text-dark">
                  Retirez votre argent, quand vous le souhaitez sans
                  complications sous 24h
                </p>
              </div>
            </div>
          </div>
          <div class="column is-4 is-block-desktop is-hidden-touch">
            <img
              class="mx-auto mt-0-widescreen is-block image"
              src="@/assets/app.png"
              alt=""
              style="zoom: 40% !important"
            />
          </div>
          <div class="column is-12 is-4-desktop">
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">
                  Parrainnez sans limites et en un clic
                </h4>
                <p class="subtitle has-text-dark">
                  Envoyez votre lien de parrainnage a vos proches
                </p>
              </div>
            </div>
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">
                  Paiement sur et securise
                </h4>
                <p class="subtitle has-text-dark">
                  Paiement via les services de paiement mobile MTN et Airtel
                </p>
              </div>
            </div>
            <div class="mb-6 is-flex">
              <span>
                <svg
                  width="48"
                  height="48"
                  viewbox="0 0 48 48"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M25.6 22.9C25.7 23 25.8 23 26 23H33C33.6 23 34 22.6 34 22C34 21.8 34 21.7 33.9 21.6L30.4 14.6C30.1 14.1 29.5 13.9 29 14.2C28.9 14.3 28.7 14.4 28.6 14.6L25.1 21.6C24.9 22 25.1 22.6 25.6 22.9ZM29.5 17.2L31.4 21H27.6L29.5 17.2ZM18.5 14C16 14 14 16 14 18.5C14 21 16 23 18.5 23C21 23 23 21 23 18.5C23 16 21 14 18.5 14ZM18.5 21C17.1 21 16 19.9 16 18.5C16 17.1 17.1 16 18.5 16C19.9 16 21 17.1 21 18.5C21 19.9 19.9 21 18.5 21ZM22.7 25.3C22.3 24.9 21.7 24.9 21.3 25.3L18.5 28.1L15.7 25.3C15.3 24.9 14.7 24.9 14.3 25.3C13.9 25.7 13.9 26.3 14.3 26.7L17.1 29.5L14.3 32.3C13.9 32.7 13.9 33.3 14.3 33.7C14.7 34.1 15.3 34.1 15.7 33.7L18.5 30.9L21.3 33.7C21.7 34.1 22.3 34.1 22.7 33.7C23.1 33.3 23.1 32.7 22.7 32.3L19.9 29.5L22.7 26.7C23.1 26.3 23.1 25.7 22.7 25.3ZM33 25H26C25.4 25 25 25.4 25 26V33C25 33.6 25.4 34 26 34H33C33.6 34 34 33.6 34 33V26C34 25.4 33.6 25 33 25ZM32 32H27V27H32V32Z"
                    fill="#7B66D5"
                  ></path>
                  <circle
                    cx="24"
                    cy="24"
                    r="23.5"
                    stroke="#7B66D5"
                  ></circle></svg
              ></span>
              <div class="ml-3">
                <h4 class="is-size-4 has-text-weight-bold mb-2">Assistance</h4>
                <p class="subtitle has-text-dark">
                  L'equipe Nkamar vous assiste 24h/24
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section has-background-primary" id="nous-contacter">
      <div class="container">
        <div class="is-vcentered columns is-multiline">
          <div class="column is-6 is-5-desktop mb-4">
            <span class="has-text-white"></span>
            <h2
              class="has-text-white mt-2 mb-3 is-size-1 is-size-3-mobile has-text-weight-bold"
            >
              Nous n'attendons que vous
            </h2>
            <p class="has-text-white">
              Notre service client est disponbile 24h/24 pour repondre a vos
              questions
            </p>
          </div>
          <div class="column is-5 ml-auto">
            <div class="mx-auto box p-6 has-background-white has-text-centered">
              <h4 class="is-size-5 mb-2 has-text-weight-bold">
                Rejoindre notre equipe
              </h4>
              <p class="has-text-dark-dark mb-4">
                Merci de renseigner votre e-mail
              </p>
              <form action="#">
                <input class="input mb-3" type="email" placeholder="E-mail" />
                <textarea
                  class="textarea"
                  placeholder="Message"
                  rows="3"
                ></textarea>
                <button class="button mt-3 is-primary is-fullwidth">
                  Soumettre
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  data(){
    return{
      open:false
    }
  }
};
</script>

<style></style>
