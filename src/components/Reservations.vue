<template>
  <div class="container-reservations container" id="section-reservations">
    <div class="takeaway">
      <div class="headline">
        <h2>Takeaway</h2>
        <p>Call +55 48 3879-7503</p>
      </div>
      <img src="../assets/takeaway.jpg" alt="" />
    </div>
    <div class="reservations">
      <div class="inner-reservations">
        <h2>Make a Reservation</h2>
        <form @submit.prevent="handleSubmit">
          <input type="text" required v-model="name" placeholder="Name" />
          <input type="email" required v-model="email" placeholder="E-mail" />
          <select v-model="guestNumber">
            <option
              v-for="option in guests"
              :key="option.value"
              :value="option.value"
            >
              {{ option.text }}
            </option>
          </select>
          <input type="date" required />
          <div class="submit">
            <button>Book a Table</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Reservations",
  data() {
    return {
      name: "",
      email: "",
      guestNumber: 2,
      emailError: "",

      guests: [
        { value: 1, text: "1 adult" },
        { value: 2, text: "2 adults" },
        { value: 3, text: "3 adults" },
        { value: 4, text: "4 adults" },
        { value: 5, text: "5 adults" },
      ],
    };
  },
  methods: {
    handleSubmit() {
      const msg = `Hi, ${this.name}! \nBooking information has been sent to ${this.email} .\nThank you ^_^`;
      alert(msg);
    },
  },
};
</script>

<style scoped>
.takeaway {
  position: relative;
  margin-bottom: 8em;
}

.takeaway h2 {
  font-size: 2.5em;
}

.takeaway img {
  margin: 2em 0;
}

.headline {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  background: var(--light);
  color: var(--dark);
  width: 15em;
  height: 2em;
  padding: 2.5em 0 3em 0;
  text-transform: uppercase;
  transform: rotate(-15deg);
}

.headline p {
  color: var(--primary);
}

.reservations {
  background: var(--primary);
  border: 2px solid var(--light);
  color: var(--light);
  margin: 1em 0;
}

.inner-reservations {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-transform: uppercase;
  padding: 1em;
  height: 35em;
}

.inner-reservations h2 {
  text-align: center;
  padding-bottom: 1em;
}

form {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 100%;
}

input,
select {
  background: none;
  color: var(--light);
}

input,
select {
  padding: 1.3em;
  margin: 0.5em 0;
  border: 1px solid var(--light);
}

input[type="text"]:focus,
input[type="date"]:focus {
  border: 2px solid var(--light) !important;
  outline: var(--light);
}

::-webkit-input-placeholder {
  color: var(--light);
}

.submit button {
  font-family: 'droid-sans-mono';
  padding: 1.8em;
  background: var(--light);
  border: none;
  color: var(--primary);
  width: 100%;
}

.submit button:hover {
  background: var(--dark);
  border: none;
  color: var(--light);
}

@media only screen and (min-width: 768px) {
  .reservations {
    margin: 1em 0 15em 0;
  }

  .inner-reservations {
    height: 40em;
    padding: 3em;
  }

  .inner-reservations h2 {
    padding-bottom: 2em;
  }

  input,
  select {
    margin: 1em;
  }

  .submit {
    padding: 1em 0.8em;
  }
}

@media only screen and (min-width: 1024px) {
  .container-reservations {
    display: flex;
    flex-direction: row-reverse;
    justify-content: space-between;
    height: 100vh;
  }

  .headline {
    left: -2em;
    width: 17em;
    padding: 2.5em 0;
  }

  .headline img {
    width: 17em;
  }

  .takeaway {
    display: flex;
    flex-direction: column;
  }

  .takeaway h2 {
    font-size: 3rem;
  }

  .takeaway {
    font-size: 1.5rem;
  }

  .takeaway img {
    margin: 3em 0 2em 0;
    width: 17em;
  }

  .reservations {
    display: flex;
    align-items: flex-end;
    justify-content: center;
    flex-direction: column;
    height: 35em;
    margin: auto 0 0 0;
  }

  .inner-reservations {
    width: 23em;
    height: 31em;
    padding: 1.5em;
  }

  .inner-reservations h2 {
    padding: 1em 0 0.5em 0;
  }
}
</style>