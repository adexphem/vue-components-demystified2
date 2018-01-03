<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <hr>
        <div>User Age: {{ userAge }}</div>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
    import { eventBus} from "../main";

    export default {
      props: ['userAge'],
      methods: {
        editAge() {
          this.userAge = 120;
          //this.$emit('ageWasEdited', this.userAge)
          eventBus.$emit('ageWasEdited', this.userAge)
        }
      }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
