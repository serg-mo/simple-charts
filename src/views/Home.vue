<template>
    <div>
        <dnd></dnd>
        <line-chart :chart-data="datacollection"></line-chart>
        <button @click="fillData()">Randomize</button>

        <!--
        <header>
            <div>{{ query }}</div>
        </header>
        <div class="ui equal width grid">
            <div class="row">
                <div class="column">
                    <div id="pie_one" class="chart pie"></div>
                </div>
                <div class="column">
                    <div id="pie_two" class="chart pie"></div>
                </div>
            </div>
            <div class="row">
                <div class="column">
                    <div id="stack" class="chart stack"></div>
                </div>
            </div>
            <div class="row" style="display: none">
                <div class="column">
                    <div id="line" class="chart line"></div>
                </div>
            </div>
            <div class="row" v-if="filtered.length > 0">
                <div class="column">
                    <div>{{ filtered.length }}</div>
                    <table id="transactions" class="ui collapsing striped small single line celled table">
                      <thead>
                        <th v-for="(value, name) in filtered[0]" title="{{ name }}">
                          {{ name }}
                        </th>
                      </thead>
                      <tbody>
                        <tr v-for="row in filtered">
                          <td v-for="value in row" title="{{ value }}">
                            {{ value }}
                          </td>
                        </tr>
                      </tbody>
                    </table>
                </div>
            </div>
        </div>
      -->
    </div>
</template>
<script type="text/javascript">
  import Dnd from '@/components/Dnd'
  import LineChart from '@/components/LineChart'

  export default {
    components: {
      LineChart, Dnd
    },
    data () {
      return {
        datacollection: {
          labels: [],
          datasets: []
        }
      }
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        this.datacollection = {
          labels: [this.getRandomInt(), this.getRandomInt()],
          datasets: [
            {
              label: 'Data One',
              backgroundColor: '#f87979',
              data: [this.getRandomInt(), this.getRandomInt()]
            }, {
              label: 'Data One',
              backgroundColor: '#f87979',
              data: [this.getRandomInt(), this.getRandomInt()]
            }
          ]
        }
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      }
    }
    /*
    data() {
      return {
        CATEGORY_RESOLUTIONS: ["category", "subcategory", "merchant"],
        TIME_RESOLUTIONS:     ["date", "week", "month"],

        category_resolution:  "category",
        category:             null,
        subcategory:          null,
        time_resolution:      "month",

        time_after:           pick_cutoff("month"),
        time_before:          format_date(new Date),

        query:                "",
        transactions:         [],
        filtered:             [],
        data:                 [],
        x:                    {},
        y:                    {},
        xy:                   {},

        charts:               [],
      },
    },
    watch: {
      category_resolution: (val) => { section_one_wrapper(); },
      category: (val)            => { section_one_wrapper(); },
      subcategory: (val)         => { 
        stack.options.title.text = `${app.category}: ${app.subcategory}`;
        stack.data.datasets.forEach((dataset, i) => {
          // if available, hide things other than the active one, show all by default
          dataset.hidden = app.subcategory ? (dataset.label != app.subcategory) : false;
        });
        stack.update();
      },

      time_after: (val)          => { section_one_wrapper(); },
      time_before: (val)         => { section_one_wrapper(); },
      time_resolution: (val)     => {
        app.time_after  = pick_cutoff(val);
        app.time_before = format_date(new Date());

        section_one_wrapper();
      },
    },

    $("body").on("keydown", key_handler);
 */
  }
</script>
<style type="text/css" scoped>
    h1 {color: green}
</style>
