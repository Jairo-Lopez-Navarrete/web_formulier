<script>
/*import confetti from 'jsconfetti';*/
export default {
  data() {
    return {
      naam: '',
      mail: '',
      klacht: 'Ik wil korting',
      klachtTekst: '',
      nieuwsbrief: false,
      textplace: 'Wat ligt er aan basis van je klacht?',
      submitted: false,
      /*jsConfetti: null,*/
    };
  },

  /*mounted() {
    this.jsConfetti = confetti.create();
  },*/

  methods: {
    submitForm() {

      this.submitted = true;

      this.naam = '';
      this.mail = '';
      this.klacht = 'Ik wil korting';
      this.klachtTekst = '';
      this.nieuwsbrief = false;
    },

    /*triggerConfetti() {
      if (this.jsConfetti) {
        this.jsConfetti({
          particleCount: 100,
          spread: 70,
          origin: { y: 0.6 },
        });
      }
    },*/
  },
};
</script>


<template>
  <div>
    <form class="form2" @submit.prevent="submitForm">
      <label for="naam">{{ naam }}</label>
      <input v-model="naam" type="text" id="naam">
      <label for="mail">{{ mail }}</label>
      <input v-model="mail" type="email" id="mail">
      <p>{{ textplace }}</p>
      <select v-model="klacht">
        <option>Ik wil korting</option>
        <option>Ik heb het verkeerde product gekocht</option>
        <option>Ik ben bang in het donker</option>
        <option>Andere...</option>
      </select>
      <textarea v-model="klachtTekst" rows="4" cols="50" name="comment" form="usrform" placeholder="geef hier je klacht weer"></textarea>
      <label>Ik wil ingeschreven worden bij de nieuwsbrief</label>
      <input v-model="nieuwsbrief" type="checkbox" value="S">
      <button type="submit">Verzenden</button>
    </form>

    <!-- Paragraaf om de ingediende waarden weer te geven -->
    <p v-if="submitted">
      Inzending:
      <br>Naam: {{ naam }}
      <br>E-mail: {{ mail }}
      <br>Klacht: {{ klacht }}
      <br>Klachttekst: {{ klachtTekst }}
      <br>Nieuwsbrief: {{ nieuwsbrief ? 'Ja' : 'Nee' }}
    </p>
  </div>
</template>

<style scoped>
.form2{
  width: 15rem;
  display: flex;
  flex-direction: column;
  margin: 1rem 0;
}
</style>