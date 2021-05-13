<template>
  <div>
    <div class="takeaway">
      <div class="headline">
        <h2>Takeaway</h2>
        <p>Call +55 48 3879-7503</p>
      </div>
      <img src="../../public/img/takeaway.jpg" alt="" />
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
}

.takeaway h2 {
  font-size: 2.5em;
  text-transform: uppercase;
}

.takeaway img {
  padding: 1em;
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
  padding: 2.5em 2em;
  transform: rotate(-15deg);
}

.headline p {
  color: var(--primary);
}

.reservations {
  background: var(--primary);
  color: var(--light);
  margin: 1em;
}

.inner-reservations {
  display: flex;
  flex-direction: column;
  justify-content: center;
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

::-webkit-input-placeholder {
  /* Chrome/Opera/Safari */
  color: var(--light);
}
::-moz-placeholder {
  /* Firefox 19+ */
  color: var(--light);
}
:-moz-placeholder {
  /* Firefox 18- */
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
</style>