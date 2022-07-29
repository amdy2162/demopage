<template>
  <!-- OPERATION: TRANSFERS -->
  <div class="operation operation--transfer">
    <h2>Transfer money</h2>
    <form class="form form--transfer">
      <input type="text" class="form__input form__input--to" />
      <input type="number" class="form__input form__input--amount" />
      <button class="form__btn form__btn--transfer">&rarr;</button>
      <label class="form__label">Transfer to</label>
      <label class="form__label">Amount</label>
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
/* OPERATIONS */
.operation {
  border-radius: 1rem;
  padding: 3rem 4rem;
  color: #333;
}

.operation--transfer {
  background-image: linear-gradient(to top left, #ffb003, #ffcb03);
}

.operation--loan {
  background-image: linear-gradient(to top left, #39b385, #9be15d);
}

.operation--close {
  background-image: linear-gradient(to top left, #e52a5a, #ff585f);
}

h2 {
  margin-bottom: 1.5rem;
  font-size: 1.7rem;
  font-weight: 600;
  color: #333;
}

.form {
  display: grid;
  grid-template-columns: 2.5fr 2.5fr 1fr;
  grid-template-rows: auto auto;
  gap: 0.4rem 1rem;
}
</style>