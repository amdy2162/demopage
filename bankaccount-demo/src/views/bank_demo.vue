<template>
  <header-Title />
  <main class="app">
    <!-- BALANCE -->
    <div class="balance">
      <div>
        <p class="balance__label">Current balance</p>
        <p class="balance__date">As of <span class="date">05/03/2037</span></p>
      </div>
      <p class="balance__value">0000€</p>
    </div>
    <data-Left />
    <function-Right />
    <!-- SUMMARY -->
    <div class="summary">
      <p class="summary__label">In</p>
      <p class="summary__value summary__value--in">0000€</p>
      <p class="summary__label">Out</p>
      <p class="summary__value summary__value--out">0000€</p>
      <p class="summary__label">Interest</p>
      <p class="summary__value summary__value--interest">0000€</p>
      <button class="btn--sort">&downarrow; SORT</button>
    </div>

    <!-- LOGOUT TIMER -->
    <p class="logout-timer">
      You will be logged out in <span class="timer">05:00</span>
    </p>
  </main>
</template>

<script>
import headerTitle from "@/components/headerTitle/index.vue";
import dataLeft from "@/components/dataLeft/index.vue";
import functionRight from "@/components/functionRight/index.vue";
export default {
  components: { headerTitle, dataLeft, functionRight },
  data() {
    return {
      account1: {
        owner: "Jonas Schmedtmann",
        movements: [200, 455.23, -306.5, 25000, -642.21, -133.9, 79.97, 1300],
        interestRate: 1.2, // %
        pin: 1111,
        movementsDates: [
          "2021-11-18T21:31:17.178Z",
          "2021-12-23T07:42:02.383Z",
          "2022-01-28T09:15:04.904Z",
          "2022-04-01T10:17:24.185Z",
          "2022-05-08T14:11:59.604Z",
          "2022-07-15T17:01:17.194Z",
          "2022-07-16T23:36:17.929Z",
          "2022-07-21T10:51:36.790Z",
        ],
        currency: "EUR",
        locale: "pt-PT", // de-DE
      },
      account2: {
        owner: "Jessica Davis",
        movements: [5000, 3400, -150, -790, -3210, -1000, 8500, -30],
        interestRate: 1.5,
        pin: 2222,
        movementsDates: [
          "2019-11-01T13:15:33.035Z",
          "2019-11-30T09:48:16.867Z",
          "2019-12-25T06:04:23.907Z",
          "2020-01-25T14:18:46.235Z",
          "2020-02-05T16:33:06.386Z",
          "2020-04-10T14:43:26.374Z",
          "2020-06-25T18:49:59.371Z",
          "2020-07-26T12:01:20.894Z",
        ],
        currency: "USD",
        locale: "en-US",
      },
    };
  },
};
</script>
<style lang="scss" scoped>
// * MAIN */
.app {
  position: relative;
  max-width: 100rem;
  margin: 4rem auto;
  display: grid;
  grid-template-columns: 4fr 3fr;
  grid-template-rows: auto repeat(3, 15rem) auto;
  gap: 2rem;
  // opacity: 0;
  transition: all 1s;
}

.balance {
  grid-column: 1 / span 2;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 2rem;
}

.balance__label {
  font-size: 2.2rem;
  font-weight: 500;
  margin-bottom: -0.2rem;
}

.balance__date {
  font-size: 1.4rem;
  color: #888;
}

.balance__value {
  font-size: 4.5rem;
  font-weight: 400;
}

/* SUMMARY */
.summary {
  grid-row: 5 / 6;
  display: flex;
  align-items: baseline;
  padding: 0 0.3rem;
  margin-top: 1rem;
}

.summary__label {
  font-size: 1.2rem;
  font-weight: 500;
  text-transform: uppercase;
  margin-right: 0.8rem;
}

.summary__value {
  font-size: 2.2rem;
  margin-right: 2.5rem;
}

.summary__value--in,
.summary__value--interest {
  color: #66c873;
}

.summary__value--out {
  color: #f5465d;
}

.btn--sort {
  margin-left: auto;
  border: none;
  background: none;
  font-size: 1.3rem;
  font-weight: 500;
  cursor: pointer;
}

/* Exceptions for interst */
.form.form--loan {
  grid-template-columns: 2.5fr 1fr 2.5fr;
}
.form__label--loan {
  grid-row: 2;
}
/* End exceptions */

.form__input {
  width: 100%;
  border: none;
  background-color: rgba(255, 255, 255, 0.4);
  font-family: inherit;
  font-size: 1.5rem;
  text-align: center;
  color: #333;
  padding: 0.3rem 1rem;
  border-radius: 0.7rem;
  transition: all 0.3s;
}

.form__input:focus {
  outline: none;
  background-color: rgba(255, 255, 255, 0.6);
}

.form__label {
  font-size: 1.3rem;
  text-align: center;
}

.form__btn {
  border: none;
  border-radius: 0.7rem;
  font-size: 1.8rem;
  background-color: #fff;
  cursor: pointer;
  transition: all 0.3s;
}

.form__btn:focus {
  outline: none;
  background-color: rgba(255, 255, 255, 0.8);
}

.logout-timer {
  padding: 0 0.3rem;
  margin-top: 1.9rem;
  text-align: right;
  font-size: 1.25rem;
}

.timer {
  font-weight: 600;
}
</style>