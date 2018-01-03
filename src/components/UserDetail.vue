<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Details:</p>
        <hr>
        <div>
            Username: {{ switchName() }}
        </div>
        <hr>
        <button @click="resetName()">Name Reset</button>
    </div>
</template>

<script>
    export default {
      props: ['name'],

      methods: {
        switchName() {
          return this.name.split("").reverse().join("");
        },
        resetName() {
          this.name = this.name.split("").reverse().join("");
          this.$emit('nameWasReset', this.name); // this will emit an event
        }
      }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
