<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Details:</p>
        <hr>
        <div>
            Username: {{ switchName() }} <br>
            User Age: {{ userAge }}
        </div>
        <hr>
        <button @click="resetName()">Name Reset</button>
    </div>
</template>

<script>
    import { eventBus } from "../main";

    export default {
      props: [
          'name',
          'userAge'
      ],

      methods: {
        switchName() {
          return this.name.split("").reverse().join("");
        },
        resetName() {
          this.name = this.name.split("").reverse().join("");
          this.$emit('nameWasReset', this.name); // this will emit an event
        }
      },

      created() {
        eventBus.$on('ageWasEdited', (res) => {
          this.userAge = res;
        })
      }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
