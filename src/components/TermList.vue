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
      pronunciation2Votes: 0
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
      console.log(
        '1: %s, 2: %s', this.pronunciation1Votes, this.pronunciation2Votes
      )
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
