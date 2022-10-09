<template>
  <div class="min-height-100">
    <!-- stats -->
    <p class="menu-label mt-3">MON HISTORIQUE DES RETRAITS</p>
    <div class="box">
      <div class="go-right pb-5">
        <b-button
        outlined
        rounded
        type="is-link"
        icon-right="eye"
        size="is-small"
        @click="preview = true"
        label="Visualiser le graphe"
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
          label="MONTANT"
          field="etat"
          sortable
          searchable
        ></b-table-column>
        <b-table-column
          label="MOTIF"
          field="etat"
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
                <!-- chart -->
                <apexchart type="area" height="350" :options="chartOptions" :series="series"></apexchart>
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
import VueApexCharts from 'vue-apexcharts'
export default {
  layout: "dashboard",
  components: {  apexchart: VueApexCharts, },
  data() {
    return {
      preview: false,
      series: [{
            name: 'Retrait de ',
            data: [{
                x: 'Dec 23 2017',
                y: null
              },
              {
                x: 'Dec 24 2017',
                y: 44
              },
              {
                x: 'Dec 25 2017',
                y: 31
              },
              {
                x: 'Dec 26 2017',
                y: 38
              },
              {
                x: 'Dec 27 2017',
                y: null
              },
              {
                x: 'Dec 28 2017',
                y: 32
              },
              {
                x: 'Dec 29 2017',
                y: 55
              },
              {
                x: 'Dec 30 2017',
                y: 51
              },
              {
                x: 'Dec 31 2017',
                y: 67
              },
              {
                x: 'Jan 01 2018',
                y: 22
              },
              {
                x: 'Jan 02 2018',
                y: 34
              },
              {
                x: 'Jan 03 2018',
                y: null
              },
              {
                x: 'Jan 04 2018',
                y: null
              },
              {
                x: 'Jan 05 2018',
                y: 11
              },
              {
                x: 'Jan 06 2018',
                y: 4
              },
              {
                x: 'Jan 07 2018',
                y: 15,
              },
              {
                x: 'Jan 08 2018',
                y: null
              },
              {
                x: 'Jan 09 2018',
                y: 9
              },
              {
                x: 'Jan 10 2018',
                y: 34
              },
              {
                x: 'Jan 11 2018',
                y: null
              },
              {
                x: 'Jan 12 2018',
                y: null
              },
              {
                x: 'Jan 13 2018',
                y: 13
              },
              {
                x: 'Jan 14 2018',
                y: null
              }
            ],
          }],
          chartOptions: {
            chart: {
              type: 'area',
              height: 350,
              animations: {
                enabled: false
              },
              zoom: {
                enabled: false
              },
            },
            dataLabels: {
              enabled: false
            },
            stroke: {
              curve: 'straight'
            },
            fill: {
              opacity: 0.8,
              type: 'pattern',
              pattern: {
                style: ['verticalLines', 'horizontalLines'],
                width: 5,
                height: 6
              },
            },
            markers: {
              size: 5,
              hover: {
                size: 9
              }
            },
            title: {
              text: 'Historique des retraits 2022',
            },
            tooltip: {
              intersect: true,
              shared: false
            },
            theme: {
              palette: 'palette1'
            },
            xaxis: {
              type: 'datetime',
            },
            yaxis: {
              title: {
                text: 'Montant'
              }
            }
          },
    };
  },
  methods: {
    cardClick(item) {
      console.log(item);
    },
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
