<template>
  <div class="">
    <!-- stats -->
    <p class="menu-label mt-3">MES PARRAINNAGES</p>
    <div class="box">
      <div class="go-right pb-5">
        <b-button
        outlined
        rounded
        type="is-link"
        icon-right="eye"
        size="is-small"
        @click="preview = true"
        label="Visualiser le diagramme"
      ></b-button>
      </div>

      <b-table paginated per-page="30">
        <b-table-column
          label="REFERENCE"
          field="reference"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="NOM"
          field="de"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="PRENOM"
          field="vers"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="TELEPHONE"
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
        <b-table-column
          label="ETAT"
          field="etat"
          sortable
          searchable
        ></b-table-column>
      </b-table>
    </div>

    <!-- MODAL -->
    <div class="modal is-active" v-if="preview" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="mx-6">
           <div class="columns is-centered">
            <div class="column box is-four-fifths">
                <br>
                <VueFamilyTree :tree="tree" @card-click="cardClick" >
                    <template v-slot:card="{item}">
                      
                           <div class="p-4">
                            <img :src="item.image ?? 'http://nkamar.tekissa.net/_nuxt/img/icon.9d628d0.png'" width="30px"  class="box p-0" alt="">
                        
                        <p class="is-size-7">{{ item.name }}</p>
                           </div>
                    </template>                
                </VueFamilyTree>
            </div>
           </div>
        </div>
      </div>
      <button class="delete is-large" @click="preview = false"></button>
    </div>

    <!--  -->
  </div>
</template>

<script>
import VueFamilyTree from "vue-family-tree";

export default {
  layout: "dashboard",
  components: { VueFamilyTree },
  data() {
    return {
      preview: false,
      tree: [
        {
          firstPerson: {
            name: "John Walker",
            image: "https://picsum.photos/300/300?random=1",
          },
          children: [
            {
              firstPerson: {
                name: "Katia",
              },
              children: [
                {
                  firstPerson: {
                    name: "Gleb",
                  },

                  children: [
                    {
                      firstPerson: {
                        name: "Rim",
                      },
                    },
                    {
                      firstPerson: {
                        name: "Leonid",
                      },
                    },
                  ],
                },
                {
                  firstPerson: {
                    name: "Olga",
                  },
                },
              ],
            },
            {
              firstPerson: {
                name: "Vitia",
              },
            },
            {
              firstPerson: {
                name: "Antonio Wild",
                image: "https://picsum.photos/300/300?random=3",
              },
              children: [
                {
                  firstPerson: {
                    name: "Kristina Wild",
                  },
                },
                {
                  firstPerson: {
                    name: "Alexey Wild",
                  },
                },
                {
                  firstPerson: {
                    name: "Viktor Wild",
                  },
                },
              ],
            },
          ],
        },
      ],
    };
  },
  methods: {
    cardClick(item) {
      console.log(item);
    },
  },
};
</script>

<style></style>
