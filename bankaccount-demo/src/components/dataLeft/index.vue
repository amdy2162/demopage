<template>
  <!-- MOVEMENTS -->
  <div class="movements">
    <div
      class="movements__row"
      v-for="(item, index) in movements"
      :key="item.value"
    >
      <div
        class="movements__type"
        :class="{ deposit: item > 0, withdrawal: item < 0 }"
      >
        <!-- <div class="movements__type movements__type--withdrawal"> -->
        {{ index + 1 }} {{ item > 0 ? "deposit" : "withdrawal" }}
      </div>
      <div class="movements__date">3 days ago</div>
      <div class="movements__value">{{ item }}</div>
    </div>
    <button class="sort" @click="btnSort">sort</button>
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      movements: [200, 455.23, -306.5, 25000, -642.21, -133.9, 79.97, 1300],
      sorted: false,
    };
  },
  methods: {
    sort(sorted) {
      console.log(sorted);
      sorted ? this.movements.sort((a, b) => a - b) : this.movements;
      console.log(this.movements);
    },
    btnSort() {
      this.sorted = !this.sorted;
      this.sort(this.sorted);
    },
  },
  computed: {
    // movements(){
    // //  return this.movements.reverse()
    // }
  },
};
</script>

<style lang="scss" scoped>
/* MOVEMENTS */

.movements {
  grid-row: 2 / span 3;
  background-color: #fff;
  border-radius: 1rem;
  overflow: scroll;
}
.sort {
  width: 100px;
  height: 50px;
  padding: 10px 20px;
  border-radius: 50px;
  background: #e52a5a;
  color: #fff;
  border: none;
}
.movements__row {
  padding: 2.25rem 4rem;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #eee;
}

.movements__type {
  font-size: 1.1rem;
  text-transform: uppercase;
  font-weight: 500;
  color: #fff;
  padding: 0.1rem 1rem;
  border-radius: 10rem;
  margin-right: 2rem;
}

.movements__date {
  font-size: 1.1rem;
  text-transform: uppercase;
  font-weight: 500;
  color: #666;
}

.deposit {
  background-image: linear-gradient(to top left, #39b385, #9be15d);
}

.withdrawal {
  background-image: linear-gradient(to top left, #e52a5a, #ff585f);
}

.movements__value {
  font-size: 1.7rem;
  margin-left: auto;
}
</style>