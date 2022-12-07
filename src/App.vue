<template>
  <div class="container">

    <div>
    <HeaderView title="Wordsmith Learning App" developerName="Deep Vira" />

    </div>
    <OutterBox :words="words" />

    <footer>
      <p>© 2022 Deep Vira</p>

    </footer>

</div>
</template>

<script>

import HeaderView from './components/HeaderView.vue'
import OutterBox from './components/OutterBox.vue'

export default {
  name: 'App',
  components: {    
    HeaderView,
    OutterBox
  },

  data(){
    return {
      words: []
    }

  },

  methods: {

    // promises

      async fetchWords(){
          const res = await fetch('https://viridian-lion-wig.cyclic.app/api')
          const data = await res.json()
          console.log( data )
          return data
      }


  },
  async created(){
    this.words = await this.fetchWords()
  }
}

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #E6E7E7;
}
.container {
  max-width: 1200px;
  margin: 10px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.2em solid black;
  padding: 30px;
  border-radius: 5px;
  display: grid;
  grid-template-rows: 0.2fr 5fr 0.02fr ;
  grid-template-columns: 1fr ;
  grid-template-areas: 
  "header "
  "question "
  "footer"
  ;
}
footer{
    margin-top: 30px;
    color: rgb(0, 0, 0);
    text-align: center;
    grid-area: footer;

}


div{
  margin-bottom: 0.1em;
}

</style>
