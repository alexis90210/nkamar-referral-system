<template>
  <div class="min-height-100">
    <!-- stats -->
    <p class="menu-label mt-3">MOM PROFILE</p>
    <div class="box">
      <div class="columns">
        <div class="column">
          <div class="media">
            <div class="media-left">
              <figure class="image is-48x48">
                <img
                  src="@/assets/photo.png"
                  alt="Placeholder image"
                  style="border-radius: 50%"
                />
              </figure>
            </div>
            <div class="media-content">
              <p class="title is-4">Alexis ngoyi</p>
              <p
                class="subtitle is-6 is-size-7 is-flex is-flex-direction-row is-justify-content-start is-align-items-center"
              >
                @_069500886
              </p>
            </div>
          </div>
        </div>

        <div class="column is-one-fifths">
          <div class="go-right">
            <b-button
              outlined
              rounded
              type="is-link"
              @click="preview = true"
              size="is-small"
              label="Modifier le compte"
            ></b-button>
          </div>
        </div>
      </div>      
    </div>

    <div class="mt-3">
        <nav class="panel box p-0">

  <a class="panel-block is-size-6">
        A propos de @Nkamar
  </a>
  <a class="panel-block is-size-6">
        Conditions d'utilisation
  </a>
  <a class="panel-block is-size-6">
       Politique de confidentialite
  </a>
  <a class="panel-block is-size-6">
        Equipe technique
  </a>
  <a class="panel-block is-size-7 py-4">
      Build version 1.2.3
  </a>


  <div class="py-4 go-right">
    <button class="button is-link" @click="isFeedback=true">
      Envoyez un feedback
    </button>
  </div>
</nav>
      </div>

    <!-- MODAL -->
    <div class="modal is-active" v-if="preview" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="mx-6 mt-6">
          <div class="columns is-centered">
            <div class="column box is-four-fifths p-4">
              <div class="m-3">
                <div class="columns is-centered">
                  <div class="column is-2">
                    <center>
                      <figure class="image">
                        <img
                          src="@/assets/photo.png"
                          alt="Placeholder image"
                          style="border-radius: 50%; width: 100px"
                        />
                      </figure>
                      <b-upload
                        v-model="file"
                        expanded
                        accept=".png,.jpg,.gip,.gif"
                        class="p-1 mt-2"
                      >
                        <a class="button is-primary is-fullwidth">
                          <span class="is-size-7">Prendre une image</span>
                        </a>
                      </b-upload>
                    </center>
                  </div>
                </div>

                <section>
                  <div class="columns">
                    <div class="column">
                      <b-field label="Nom">
                        <b-input></b-input>
                      </b-field>
                    </div>
                    <div class="column">
                      <b-field label="Prenom">
                        <b-input></b-input>
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Email">
                        <b-input type="email" value="john@doe" maxlength="30">
                        </b-input>
                      </b-field>
                    </div>
                    <div class="column">
                      <b-field label="Pseudo">
                        <b-input value="johnsilver" maxlength="30"></b-input>
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Password">
                        <b-input type="password" password-reveal> </b-input>
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Description">
                        <b-input maxlength="200" type="textarea"></b-input>
                      </b-field>
                    </div>
                  </div>
                </section>

                <div class="go-right">
                  <b-button
                    rounded
                    type="is-link"
                    @click="preview = true"
                    label="Valider"
                  ></b-button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <button class="delete is-large" @click="preview = false"></button>
    </div>

    <!--  -->

    <!-- MODAL -->
    <div class="modal is-active" v-if="isFeedback" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="mx-6 mt-6">
          <div class="columns is-centered">
            <div class="column box is-four-fifths p-4">
              <div class="m-3">
                <p class="menu-label mt-3">MESSAGE FEEDBACK</p>
                <section>
           
                  <div class="columns">
                    <div class="column">
                      <b-field label="Description">
                        <b-input maxlength="200" type="textarea"></b-input>
                      </b-field>
                    </div>
                  </div>
                </section>

                <div class="go-right">
                  <b-button
                    rounded
                    type="is-link"
                    @click="isFeedback = true"
                    label="Soumetre"
                  ></b-button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <button class="delete is-large" @click="isFeedback = false"></button>
    </div>

    <!--  -->
  </div>
</template>

<script>
export default {
  layout: "dashboard",
  components: {},
  data() {
    return {
      preview: false,
      isFeedback:false,
      file: {},
    };
  },
  methods: {},
};
</script>

<style>
.min-height-100 {
  height: 100vh;
  max-height: auto;
  min-height: 100vh;
}
</style>
