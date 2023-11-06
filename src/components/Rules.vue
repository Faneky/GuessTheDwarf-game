<script setup>

let x = Math.floor(Math.random() * 13);


</script>

<template>
  <div class="container">
    <div class="dwarf-img">
      <img :src="`/src/assets/${x}.svg`" alt="img">
    </div>
    <div class="rulesOfGame">
      <h1>Guess the Dwarf</h1>
      <ol>
         <li>A random image of one of the 12 dwarves from the Hobbit will appear on the screen.</li>
         <li>You need to enter the name of this dwarf in the first input field.</li>
         <li>Then, enter the age of the dwarf in the second input field.</li>
         <p>If the age of a dwarf was not declared, leave it empty</p>
         <li>Press the "Submit" button to submit your answer.</li>
      </ol>
      <ul>
         <p>Checking the Answer:</p>
         <li>If your answer matches the name and age of the dwarf in the image, you win.</li>
         <li>If you didn't guess correctly, you will be given another chance to guess, but with a different dwarf.</li>
      </ul>
      <p>Victory:</p>
      <p>You win when you correctly guess one of the dwarves.</p>
      <p>Good luck and have fun: May luck be with you, and may the game bring you enjoyment!</p>
   </div>
  </div>
</template>



<style scoped>
</style>
<style>

.rulesOfGame{
   margin-left: 50px;
}
h1{
  font-style: 52px;
}
.rulesOfGame > *{
   color: #aaa5a5;
   line-height: 1.8;
   font-size: 18px;
}
.dwarf-img img{
  width: 125px;
}

</style>
