<template>
  <v-card class="card_border_dadius px-4">
    <v-row justify="space-between">
      <v-col md="3">
        <h3 class="gray--text title">Muon Requests History</h3>
      </v-col>
      <v-col md="4" class="text-right">
        <div class="bg_days_btn">
          <v-btn
            :class="[whichActive === 1 ? 'active_day' : 'deActive_day']"
            elevation="0"
            rounded
            @click="whichActive = 1"
            >1d
          </v-btn>
          <v-btn
            elevation="0"
            rounded
            :class="[whichActive === 7 ? 'active_day' : 'deActive_day']"
            @click="whichActive = 7"
            >7d
          </v-btn>
          <v-btn
            elevation="0"
            rounded
            :class="[whichActive === 14 ? 'active_day' : 'deActive_day']"
            @click="whichActive = 14"
            >14d
          </v-btn>
          <v-btn
            elevation="0"
            rounded
            :class="[whichActive === 21 ? 'active_day' : 'deActive_day']"
            @click="whichActive = 21"
            >21d
          </v-btn>
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <highcharts
          class="highcharts-figure"
          :options="chartOptions"
        ></highcharts>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
import { Chart } from 'highcharts-vue'

export default {
  name: 'MuonRequestsHistory',
  components: { highcharts: Chart },
  data() {
    return {
      whichActive: 1,
      chartOptions: {
        chart: {
          zoomType: 'x',
        },
        color: {
          linearGradient: { x1: 0, x2: 0, y1: 0, y2: 1 },
          stops: [
            [0, '#003399'],
            [1, '#3366AA'],
          ],
        },
        xAxis: {
          type: 'datetime',
        },
        legend: {
          enabled: false,
        },
        color: {
          linearGradient: { x1: 0, x2: 0, y1: 0, y2: 1 },
          stops: [
            [0, '#003399'],
            [1, '#3366AA'],
          ],
        },
        plotOptions: {
          area: {
            fillColor: {
              linearGradient: {
                x1: 0,
                y1: 0,
                x2: 0,
                y2: 1,
              },
              stops: [
                [0, '#003399'],
                [1, '#3366AA'],
              ],
            },
            marker: {
              radius: 2,
            },
            lineWidth: 1,
            states: {
              hover: {
                lineWidth: 1,
              },
            },
            threshold: null,
          },
        },
        series: [],
      },
    }
  },
  methods: {
    async httpJson(theUrl) {
      fetch(theUrl, {
        method: 'GET',
      })
        .then((response) => response.text())
        .then((res) => {
          const newData = JSON.parse(res)
          this.chartOptions.series = [{ data: newData }]
        })
    },
  },
  created() {
    this.httpJson(
      'https://cdn.jsdelivr.net/gh/highcharts/highcharts@v7.0.0/samples/data/usdeur.json'
    )
  },
}
</script>

<style scoped>
.card_border_dadius {
  border-radius: 20px !important;
}
.title {
  font-family: 'Lato';
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
}
.bg_days_btn {
  background-color: #eaeaef;
  float: right;
  border-radius: 25px;
}
.active_day {
  background-color: #e0e0ea !important;
}
.deActive_day {
  background-color: #eaeaef !important;
  color: #88889a;
}
</style>
