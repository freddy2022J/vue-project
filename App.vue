<template>
  <div>
    <h2>Prime Number </h2>
    <input type="number" v-model="number" placeholder="Enter a number" />
    <button @click="checkPrime">Check</button>
    <p v-if="result !== null">The number {{ number }} is {{ result }}.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number: null,
      result: null
    };
  },
  methods: {
    checkPrime() {
      if (this.number <= 0) {
        this.result = 'not a prime number';
        return;
      }

      for (let i = 2; i <(this.number); i++) {
        if (this.number % i === 0) {
          this.result = 'not a prime number';
          return;
        }
      }

      this.result = 'a prime number';
    }
  }
};
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
