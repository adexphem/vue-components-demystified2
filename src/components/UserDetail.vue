<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Details:</p>
        <hr>
        <div>
            Username: {{ switchName() }}
        </div>
    </div>
</template>

<script>
    export default {
      props: ['name'],

      methods: {
        switchName() {
          return this.name.split("").reverse().join("");
        }
      }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
