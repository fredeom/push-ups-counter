<script>

export default {
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    addPushUps() {
        const dayNum = new Date().getDay();
        const dayName = "day" + dayNum;
        if (!localStorage[dayName]) {
          localStorage[dayName] = 0;
        }
        localStorage[dayName] = +localStorage[dayName] + this.counter;
        this.counter = 0;
        window.location.href = window.location.href;
    }
  }
}

</script>

<template>
    <div>
        <input type="number" v-model="counter" />
        <button @click="addPushUps()">Add</button>
    </div>
    {{ counter }}
</template>

<style scoped>
</style>