<template>
  <section>
    <div v-if="'text' in s" v-text="s.text" style="color: #777; padding: 0.8em; font-size: 0.7em" />

    <div v-else class="row" :class="s.mark">
      <div class="title">{{ s.title }}</div>
      <div class="time">
        <span class="from">{{ s.from }}</span>
        <span class="to">{{ s.to }}</span>
      </div>

      <div class="info">
        <div class="who" v-if="is('who')">
          <i class="fas fa-user"></i> {{ s.who }}</div>

        <div class="type" v-if="is('type')">
          <i class="fas" :class="icon"></i> {{ s.type }}</div>

        <div class="place" v-if="is('place')">
          <i class="fas fa-map-marker-alt"></i> {{ s.place }}</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "item",
  props: ['subject', 'prev'],
  computed: {
    s() { return this.subject },

    icon() {
      if (this.subject.type === 'практика')
        return 'fa-bug'

      if (this.subject.type === 'лекция')
        return 'fa-graduation-cap'

      return 'fa-question'
    },

    isWho() {
      return this.s.who && this.s.who !== this.prev.who
    },
    isType() {
      return this.s.type && this.s.type !== this.prev.type
    },
    isPlace() {
      return this.s.place && this.s.place !== this.prev.place
    }
  },
  methods: {
    is(field) {
      return this.s[field] && this.s[field] !== this.prev[field]
    }
  }
}
</script>

<style scoped>

.row {
  display: grid;
  grid-template-columns: 70px auto;
  grid-template-rows: 1fr auto;

  border-bottom: 1px solid #ddd;
  padding: 1px 0;
}

section:first-of-type  > .row:first-of-type {
  border-top: 1px solid #ddd;
}

.row.blue {
  /*background: #e3f2fd;*/
  background: #e9f5fd;
}

.row.yellow {
  background: #fff8e1;
}



.time {
  grid-row: 1 / 3;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  transform: scale(1.2);
}

.to {
  transform: scale(0.7);
  color: #7c7c7c;
}

.title {
  grid-column: 2 / 3;
  padding: 7px 1.2em;

  font-size: 1.1em;
  font-family: 'Open Sans', sans-serif;
  font-weight: 600;
  /*white-space: pre-wrap;*/
}

.info {
  grid-column: 2 / 3;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;

  padding-bottom: 8px;
  font-size: 0.75rem;
  color: #878787;
}

.info > * {
  white-space: pre-wrap;
}

</style>
