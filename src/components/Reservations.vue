<template>
  <div class="container-reservations container">
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

        <form>
          <input
            type="text"
            id="firstName"
            name="firstName"
            class="input"
            placeholder="First Name"
          />
          <input
            type="text"
            id="lastName"
            name="lastName"
            placeholder="Last Name"
          />
          <input type="text" id="eMail" name="eMail" placeholder="Email" />
          <input type="date" id="date" name="date" />
          <input type="submit" value="Book a Table" />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Reservations",
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
  height: 30em;
}

.inner-reservations h2 {
  text-align: center;
  padding-bottom: 1em;
}

form {
  display: flex;
  flex-direction: column;
}

input {
  padding: 1.3em;
  margin: 0.5em;
  border: 1px solid var(--light);
  background: none;
  color: var(--light);
}

input[type="text"]:focus,
input[type="date"]:focus {
  border: 2px solid var(--light) !important;
  outline: var(--light);
}

/* Chrome/ Opera/ Safari */
::-webkit-input-placeholder {
  color: var(--light);
}

input[type="submit"] {
  background: var(--light);
  border: none;
  color: var(--primary);
}

input[type="submit"]:hover {
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

  input {
    margin: 1em;
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
    justify-content: flex-end;
    flex-direction: column;
    height: 31em;
    margin: auto 0 0 0;
  }

  .inner-reservations {
    width: 23em;
    height: 30em;
    padding: 1.5em;
  }

  .inner-reservations h2 {
    padding: 1em 0 0.5em 0;
  }
}
</style>