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
          <progress class="mb-0 progress is-danger" v-else value="70" max="100">
            70%
          </progress>

          <div class="go-right">20</div>
        </div>
      </div>
    </div>
    <hr class="dropdown-divider my-5" aria-role="menuitem" />
    <p class="menu-label mt-3">FORMULE</p>
    <div class="columns">
      <div class="column is-6">
        <!-- Pack standards -->
        <div class="card has-background-link-dark ">
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
      
      <div class="column is-6">
        <!-- Pack standards -->
        <div class="card has-background-info ">
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
      
    </div>

    <hr class="dropdown-divider my-5" aria-role="menuitem" />
    <p class="menu-label mt-3">TRANSACTIONS RECENTES</p>

    <b-table paginated per-page="30">
        <b-table-column label="REFERENCE" field="reference" sortable searchable></b-table-column>
        <b-table-column label="DE" field="de" sortable searchable></b-table-column>
        <b-table-column label="VERS" field="vers" sortable searchable></b-table-column>
        <b-table-column label="MOTIF" field="motif" sortable searchable></b-table-column>
        <b-table-column label="DATE" field="date" sortable searchable></b-table-column>
    </b-table>
   </div>

  </div>
</template>

<script>
export default {
  layout: "dashboard",
  data() {
    return {
      isLoadingStats: false,
    };
  },
};
</script>

<style>
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
</style>
