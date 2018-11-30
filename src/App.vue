<template>
  <div id="app">
    <h1>Rock-Paper-Scissor <i class="fas fa-rocket"></i></h1>
    <small>Crafted By : <a href="https://www.github.com/abhay676" target="_blank">Abhay Goswami</a></small>
    <div class="container">
      <Score
              :userScore = "userScore"
              :sysScore = "sysScore"
              :userChoice = "userChoice"
              :sysChoice = "sysChoice"
              :istrue = "istrue"
      ></Score>
      <choices
              @userChoice = "systemChoice"
      ></choices>
    </div>
  </div>
</template>

<script>
    import choices from './components/choices.vue';
    import Score from './components/Score.vue';

export default {
  name: 'app',
    components: {
      choices,
        Score
    },
    data() {
      return {
        userScore: 0,
        sysScore: 0,
        userChoice: '',
        sysChoice: '',
        istrue: false
      };
    },
    methods: {
      systemChoice(q) {
          this.userChoice = q;
          if (this.userChoice === 'reset') {
              this.userScore = 0;
              this.sysScore = 0;
              this.istrue = false;
          } else if (this.userChoice != 'reset') {
              this.istrue = true;
              let sys = ['rock', 'paper', 'scissor'];
              let choice= sys[Math.floor(Math.random() * sys.length)];
              this.sysChoice = choice;
           if (this.userChoice === 'rock' && this.sysChoice === 'scissor') {
                  this.userScore++ ;
              } else if (this.userChoice === 'paper' && this.sysChoice === 'rock') {
                  this.userScore++ ;
              }  else  if (this.userChoice === 'scissor' && this.sysChoice === 'paper') {
                  this.userScore++ ;
              } else if (this.userChoice === this.sysChoice) {

              }
              else {
                  this.sysScore++;
              }
          }
       }
    }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
