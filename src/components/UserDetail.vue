<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Details:</p>
        <hr>
        <div>
            Username: {{ name }}
        </div>
    </div>
</template>

<script>
    export default {
      props: ['name']
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
