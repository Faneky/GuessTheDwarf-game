<script setup>

import { ref } from 'vue';
import data from '../data.json'

let name = ref('')
let age = ref('')
let x = Math.floor(Math.random() * 13);
let showWinComponent = ref(false);

function recognazition(){
  for(let i = 0; i < data.length; i++){
    let ageData = 0;
    //Проверка совпадения по id
    if(x === data[i].id){
      console.log(data[i].name)
      //Проверка на дату рождения, при значении null
      if(data[i].yearOfBirth !== null){
        ageData = 3021 - data[i].yearOfBirth
        console.log(ageData)
      } else {
        ageData = ''
      }
      //Проверка на совпадение введенных данных
      if(age.value === ageData && name.value === data[i].name){
        showWinComponent.value = true;
        break;
      }
    }
  }
}
recognazition()
</script>

<template>
  <div v-if="showWinComponent" class="win">
      <h1>You win!</h1>
      <img src="../assets/winGif.gif" alt="gif">
   </div>

   <div v-else="showWinComponent" class="container">
    <div class="dwarf-img">
      <img :src="`../assets/${x}.svg`" alt="img">
      <!-- <img :src="`src/assets/${x}.svg`" alt="img"> -->
    </div>
    <div class="">
      <form class='quiz' action="">
      <label>
        <input class="input" v-model="name" id="name" type="text" placeholder="name">
      </label>
      <label>
        <input class="input" v-model.number="age" type="number" placeholder="age">
      </label>
      <button @click="recognazition" class="button" type="submit">
        Submit
      </button>
    </form>
    </div>
  </div>
</template>

<style>

body{
  padding: 0;
  margin: 0;
  background-color: rgb(27, 23, 23);
}
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2em;
}
.dwarf-img img{
  width: 125px;
}
  .quiz{
    display: flex;
    flex-direction: column;
    justify-self: unset;
    align-items: center;
    margin-left: 20px;
  }
  .input{
    background-color: beige;
    padding: 7px 0px 7px 5px;
    outline-color: #fff;
  }
  .quiz > *{
    margin-bottom: 15px;
  }
  .button{
    width: 100%;
    color: #fff;
    background-color: #000;
    padding: 10px 0;
    border: 0px;
    cursor: pointer;
  }
.win{
  text-align: center;
  margin-top: 20px;
  color: #fff;
}
.win h1{
  margin-bottom: 20px;
}
</style>