<template>
  <div class='term-list'>
    <div class='term-box'>
      <div class='term'>
        <h2> GIF </h2>
        <p class='term-definition'>
          a lossless format for image files that supports both animated and
          static images.
        </p>
        <div class='term-pronunciations'>
          <input type='radio' v-model='selected' name='vote' :value='0' />
          <kendo-button
            icon='volume-up'
            @click='playSound("http://bit.ly/2HHjJio")'
          > gif
          </kendo-button>
          <input type='radio' v-model='selected' name='vote' :value='1' />
          <kendo-button
            icon='volume-up'
            @click='playSound("http://bit.ly/2plmOO2")'
          > jif
          </kendo-button>
        </div>
        <div class='term-voting'>
          <kendo-button class='k-primary' @click='onVote'>
            VOTE
          </kendo-button>
        </div>
      </div>
      <div class='term-voting'>
        <h2> Voting Results </h2>
        <div class='term-vote-chart'>
          <kendo-chart
            :series-defaults-type="'donut'"
            :chart-area-background="''"
            :series="series"
            :tooltip="tooltip" >
          </kendo-chart>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'term-list',
  data () {
    return {
      selected: 0,
      pronunciation1Votes: 0,
      pronunciation2Votes: 0,
      tooltip: { visible: true, template: '#= value # votes' }
    }
  },
  methods: {
    playSound (sound) {
      if (sound) {
        let audio = new Audio(sound)
        audio.play(sound)
      }
    },
    onVote () {
      if (this.selected) this.pronunciation2Votes++
      else this.pronunciation1Votes++
    }
  },
  computed: {
    series: function () {
      return [{
        data: [{
          category: 'gif',
          value: this.pronunciation1Votes,
          color: '#fff258'
        }, {
          category: 'jif',
          value: this.pronunciation2Votes,
          color: '#58d9ff'
        }]
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.term-box {
  background-color: rgba(255, 255, 255, 0.95);
  border: solid black 3px;
  height: 235px;
  margin: 1em auto;
  max-width: 800px;
  padding: 5px;
}

.term {
  border-right: solid black 1px;
  float: left;
  padding: 10px;
  width: 45%;
}

.submit-vote {
  float: right;
  margin: 5px 5px 0 0;
}

.term-voting {
  float: right;
  padding: 10px;
  text-align: right;
}

.k-chart {
  height: 200px;
}
</style>
