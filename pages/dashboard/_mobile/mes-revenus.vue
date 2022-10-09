<template>
  <div class="min-height-100">
    <!-- stats -->
    <p class="menu-label mt-3">MES REVENUS </p>
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
                <apexchart type="bar" height="350" :options="chartOptions" :series="series"></apexchart>
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
// import VueApexCharts from 'vue-apexcharts'

if(process.client) {
 var VueApexCharts = require('vue-apexcharts')
}

export default {
  layout: "dashboard",
  components: {  apexchart: VueApexCharts, },
  data() {
    return {
      preview: false,
     
      series: [{
            name: 'Gain de ',
            data: [2.3, 3.1, 4.0, 10.1, 4.0, 3.6, 3.2, 2.3, 1.4, 0.8, 0.5, 0.2]
          }],
          chartOptions: {
            chart: {
              height: 350,
              type: 'bar',
            },
            plotOptions: {
              bar: {
                borderRadius: 10,
                dataLabels: {
                  position: 'top', // top, center, bottom
                },
              }
            },
            dataLabels: {
              enabled: true,
              formatter: function (val) {
                return val + " F";
              },
              offsetY: -20,
              style: {
                fontSize: '12px',
                colors: ["#304758"]
              }
            },
            
            xaxis: {
              categories: ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
              position: 'top',
              axisBorder: {
                show: false
              },
              axisTicks: {
                show: false
              },
              crosshairs: {
                fill: {
                  type: 'gradient',
                  gradient: {
                    colorFrom: '#D8E3F0',
                    colorTo: '#BED1E6',
                    stops: [0, 100],
                    opacityFrom: 0.4,
                    opacityTo: 0.5,
                  }
                }
              },
              tooltip: {
                enabled: true,
              }
            },
            yaxis: {
              axisBorder: {
                show: false
              },
              axisTicks: {
                show: false,
              },
              labels: {
                show: false,
                formatter: function (val) {
                  return val + " F";
                }
              }
            
            },
            title: {
              text: 'Historique des revenus , 2022',
              floating: true,
              offsetY: 330,
              align: 'center',
              style: {
                color: '#444'
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
