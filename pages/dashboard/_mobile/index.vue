<template>
  <div class="">
    <!-- stats -->
    <p class="menu-label mt-3">TABLEAU DE BORD</p>
    <div class="box pt-5">
      <div class="stats">
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
                  class="subtitle is-6 is-flex is-flex-direction-row is-justify-content-start is-align-items-center"
                >
                  0
                  <svg
                    style="width: 24px; height: 24px; zoom: 70%"
                    viewBox="0 0 24 24"
                  >
                    <path
                      fill="currentColor"
                      d="M18 5V3H7V16H5V18H7V21H9V18H13V16H9V13H17V11H9V5H18Z"
                    />
                  </svg>
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
                size="is-small"
                @click="isRetrait = true"
                label="Retrait d'argent"
              ></b-button>
            </div>
          </div>
        </div>
        <div class="columns">
          <div class="column px-5 py-0">
            <p class="fs-welcome">Parrainages</p>
            <progress
              class="mb-0 progress is-link"
              v-if="isLoadingStats"
              max="100"
            >
              30%
            </progress>

            <progress class="mb-0 progress is-link" v-else value="30" max="100">
              30%
            </progress>

            <div class="go-right">30</div>
          </div>

          <div class="column px-5 py-0">
            <p class="fs-welcome">Filleuls actifs</p>
            <progress
              class="mb-0 progress is-success"
              v-if="isLoadingStats"
              max="100"
            >
              30%
            </progress>
            <progress
              class="mb-0 progress is-success"
              v-else
              value="70"
              max="100"
            >
              70%
            </progress>

            <div class="go-right">70</div>
          </div>

          <div class="column px-5 py-0">
            <p class="fs-welcome">Filleuls inaptes</p>
            <progress
              class="mb-0 progress is-success"
              v-if="isLoadingStats"
              max="100"
            >
              30%
            </progress>
            <progress
              class="mb-0 progress is-danger"
              v-else
              value="70"
              max="100"
            >
              70%
            </progress>

            <div class="go-right">20</div>
          </div>
        </div>
      </div>
      <hr class="dropdown-divider my-5" aria-role="menuitem" />
      <p class="menu-label mt-3">FORMULE</p>
      <div class="columns">
        <b-tooltip
          label="Vous etes soucrit"
          always
          class="column is-6"
          position="is-bottom"
        >
          <div class="">
            <!-- Pack standards -->
            <div class="card has-background-link-dark">
              <div class="card-content">
                <div class="content">
                  <span class="is-size-7 has-text-light">DEBUTANT</span>
                  <div class="is-size-5 has-text-light my-2">
                    <span class="pr-3">5 000</span>
                    <svg
                      style="width: 24px; height: 24px; zoom: 70%"
                      viewBox="0 0 24 24"
                    >
                      <path
                        fill="currentColor"
                        d="M18 5V3H7V16H5V18H7V21H9V18H13V16H9V13H17V11H9V5H18Z"
                      />
                    </svg>
                  </div>
                  <div style="zoom: 80%" class="">
                    <b-button
                      outlined
                      rounded
                      type="is-light"
                      size="is-small"
                      label="Actif"
                    ></b-button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </b-tooltip>

        <b-tooltip
          label="Formule pas non disponible"
          always
          class="column is-6"
          position="is-top"
          type="is-warning"
        >
          <div class="">
            <!-- Pack standards -->
            <div class="card has-background-info">
              <div class="card-content">
                <div class="content">
                  <span class="is-size-7 has-text-light">EXPERT</span>
                  <div class="is-size-5 has-text-light my-2">
                    <span class="pr-3">50 000</span>
                    <svg
                      style="width: 24px; height: 24px; zoom: 70%"
                      viewBox="0 0 24 24"
                    >
                      <path
                        fill="currentColor"
                        d="M18 5V3H7V16H5V18H7V21H9V18H13V16H9V13H17V11H9V5H18Z"
                      />
                    </svg>
                  </div>
                  <div style="zoom: 80%" class="">
                    <b-button
                      outlined
                      rounded
                      type="is-light"
                      size="is-small"
                      label="Non disponible"
                    ></b-button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </b-tooltip>
      </div>

      <hr class="dropdown-divider my-5" aria-role="menuitem" />
      <p class="menu-label mt-3">TRANSACTIONS RECENTES</p>

      <b-table paginated per-page="30">
        <b-table-column
          label="REFERENCE"
          field="reference"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="DE"
          field="de"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="VERS"
          field="vers"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="MOTIF"
          field="motif"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="DATE"
          field="date"
          sortable
          searchable
        ></b-table-column>
      </b-table>
    </div>

    <!-- MODAL -->
    <div class="modal is-active" v-if="isRetrait" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="mx-6 mt-6">
          <div class="columns is-centered">
            <div class="column box is-two-fifths p-4">
              <div class="m-3">
                <p class="menu-label mt-3">RETRAIT DE COMPTE</p>
                <section>
                  <div class="columns is-centered">
                    <div class="column is-6">
                      <center>
                        <b-tooltip
                          label="Retrait via"
                          :dashed="paiement == 1 ? true : false"
                          :always="paiement == 1 ? true : false"
                          position="is-left"
                          type="is-danger"
                        >
                          <img
                            src="@/assets/airtel.png"
                            style="border-radius: 1%; cursor: pointer"
                            width="50px"
                            class="mx-4"
                            @click="paiement = 1"
                          />
                        </b-tooltip>

                        <b-tooltip
                          label="Retrait via"
                          :dashed="paiement == 2 ? true : false"
                          :always="paiement == 2 ? true : false"
                          position="is-right"
                          type="is-warning"
                        >
                          <img
                            src="@/assets/mtn.png"
                            style="border-radius: 1%; cursor: pointer"
                            width="50px"
                            class="mx-4"
                            @click="paiement = 2"
                          />
                        </b-tooltip>
                      </center>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Montant">
                        <b-numberinput :controls="false"></b-numberinput>
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
                    @click="isRetrait = true"
                    label="Valider"
                  ></b-button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <button class="delete is-large" @click="isRetrait = false"></button>
    </div>

    <!--  -->
  </div>
</template>

<script>
export default {
  layout: "dashboard",
  data() {
    return {
      isLoadingStats: false,
      isRetrait: false,
      paiement: 0,
    };
  },
};
</script>

<style></style>
