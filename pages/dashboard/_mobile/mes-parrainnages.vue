<template>
  <div class="min-height-100">
    <!-- stats -->
    <p class="menu-label mt-3">MES PARRAINNAGES</p>

    <div class="columns my-2" style="zoom:80%">
      <b-tooltip label="Nouveau parrainnage" always class="column is-12"  position="is-top" type="is-warning">
      <div class="">
        <!-- Pack standards -->
        <div class="card has-background-link-dark ">
          <div class="card-content">
            <div class="content">
              <span class="is-size-7 has-text-light">VOTRE IDENTIFIANT</span>
              <div class="is-size-5 has-text-light my-2">
                <span class="pr-3">ANM_0695008543</span>                
              </div>
              <div style="zoom: 80%" class="">
                <b-button
                  outlined
                  rounded
                  type="is-light"
                  @click="isParrainnage = true"
                  label="Parrainer un proche"
                ></b-button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </b-tooltip>
    </div>
    
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
                      
                           <div class="p-4 box is-flex is-align-items-center">
                            <img :src="item.image ?? 'http://nkamar.tekissa.net/_nuxt/img/icon.9d628d0.png'" width="30px" 
                             class="p-0" alt="">
                             <b-tooltip :label="item.data + ' Filleuls'" always>
                                <p class="is-size-7 pl-3">{{ item.name }}</p>
                            </b-tooltip>
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

      <!-- MODAL -->
      <div class="modal is-active" v-if="isParrainnage" style="z-index: 100">
      <div class="modal-background"></div>
      <div class="modal-content">
        <div class="mx-6 mt-6">
          <div class="columns is-centered">
            <div class="column box is-two-fifths p-4">
              <div class="m-3">
                <p class="menu-label mt-3">NOUVEAU PARRAINNAGE</p>
                <section>              

                  <div class="columns">
                    <div class="column">
                      <b-field label="Lien de parrainnage">
                        <b-input v-model="lien_parrainnage" onclick="this.select()"></b-input>
                      </b-field>
                    </div>
                  </div>
           
               
                </section>

                <div class="go-right mt-5">
                  <b-button
                    rounded
                    type="is-link"
                    @click="copy"
                    label="Copier"
                  ></b-button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <button class="delete is-large" @click="isParrainnage = false"></button>
    </div>

    <!--  -->
  </div>
</template>

<script>
if(process.client) {
  document.addEventListener('keydown', (e) => {
    e = e || window.event;
    if(e.keyCode == 116){
        e.preventDefault();
    }
});
}

import VueFamilyTree from "vue-family-tree";

export default {
  layout: "dashboard",
  components: { VueFamilyTree },
  data() {
    return {
      preview: false,
      isParrainnage:false,
      lien_parrainnage:'http://localhost:3000/je-suis-parrain/AMN_069500886',
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
                data:12
              },
              children: [
                {
                  firstPerson: {
                    name: "Gleb",
                    data:12
                  },

                  children: [
                    {
                      firstPerson: {
                        name: "Rim",
                        data:12
                      },
                    },
                    {
                      firstPerson: {
                        name: "Leonid",
                        data:12
                      },
                    },
                  ],
                },
                {
                  firstPerson: {
                    name: "Olga",
                    data:12
                  },
                },
              ],
            },
            {
              firstPerson: {
                name: "Vitia",
                data:12
              },
            },
            {
              firstPerson: {
                name: "Antonio Wild",
                image: "https://picsum.photos/300/300?random=3",
                data:12
              },
              children: [
                {
                  firstPerson: {
                    name: "Kristina Wild",
                    data:12
                  },
                },
                {
                  firstPerson: {
                    name: "Alexey Wild",
                    data:12
                  },
                },
                {
                  firstPerson: {
                    name: "Viktor Wild",
                    data:12
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

    copy(){
      try {
        if (!navigator.clipboard) {
          // Clipboard API not available
          return;
        }
        
        navigator.clipboard.writeText(this.lien_parrainnage);
        this.$buefy.snackbar.open({
          message:'Copie ok',
          type:'is-success'
        })
        this.isParrainnage = false
      } catch (error) {
        console.log(error);
      }
    }
  },
};
</script>

<style>
.min-height-100 {
    height:100vh;
    max-height: auto;
    min-height: 100vh;
}
</style>
