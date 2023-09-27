<template>
  <div class="container">
    <h1>ALLES GUTE ZUM GEBURTSTAG! (nachträglich)</h1>
    <div class="content-wrap">
      <button id="checkbutton" v-if="count < 6" @click="increase">
        click me, kleo
      </button>
      <p v-if="count === 1">Du bist</p>
      <p v-if="count === 2">Der beste</p>
      <p v-if="count === 3">Große bruder</p>
      <p v-if="count === 4">den man sich wünschen kann</p>
      <p v-if="count === 5">
        Und hiermit schenke ich dir den 2. Teil deines Geschenkens (nochmal
        klicken)
      </p>
      <input
        v-if="count == 6"
        id="input"
        type="text"
        placeholder="Bitte den code eingeben"
        v-model="inputValue"
      />
      <button @click="checkcode()" v-if="count == 6">submit</button>
      <p v-if="count === 7">
        Hier wird ein Portofolio von Kleo Bochmann entstehen! (Ich erkläre dir
        kurz was das ist :P)
      </p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      count: 0,
      inputValue: "",
    };
  },
  methods: {
    increase() {
      this.count++;
    },
    checkcode() {
      if (this.inputValue === "52345") {
        console.log(this.inputValue);
        this.count++;
      }
    },
  },
};
</script>
<style>
h1 {
  position: absolute;
  top: 10%;
  left: 20%;
  font-family: "Press Start 2P", cursive;
  font-size: 18px;
  word-wrap: break-word;
  width: 270px;
  padding: 5px;
}
.container {
  display: grid;
  place-content: center;
  height: 100vh;
}
.content-wrap {
  font-family: "Press Start 2P", cursive;
}
#checkbutton {
  position: absolute;
  top: 20%;
  left: 0%;
  width: 100%;
  height: 100px;
  border: none;
  background-color: red;
  font-size: 50px;
  font-weight: 600;
}
</style>
