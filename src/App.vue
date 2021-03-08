<template>
  <div>
    <h1 id="title">Welcome to Guess game!</h1>
    <div id="form">
      <input v-model = 'guess' type="number" placeholder="Enter a number" />
      <button @click='onGuess' class="guess-btn">Guess</button>
    </div>
    <p>{{guess}}</p>
  </div>
</template>
<style scoped>
#title {
  text-align: center;
}
#form {
  text-align: center;
}

input {
  margin: 0px 5px;

}

.guess-btn{
  background-color: black;
  color:white;
  border: None;
  width: 60px;
  height: 25px;
  border-radius: 15%;
}
</style>

<script>
export default {
  data(){
    return{
      guess: 0,
      secretNum: Math.round(Math.random() * 10) 
    }
  },
  methods:{
    onGuess(){
      let msg;
      if(this.guess > this.secretNum){
        msg = 'your guess was too big'
      }
      else if(this.guess < this.secretNum){
        msg = 'your guess was too small'
      }
      else{
        msg = 'you are correct'
        this.secretNum = Math.round(Math.random() * 10)
      }
      alert(msg)
    }
  }
}
</script>