<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User! {{ username }}, age: {{ userAge }}</p>
        <button @click="changeName">Change User Name</button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :name="username" :userAge="userAge"
                                 @nameWasReset="username = $event"></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge="userAge" @ageWasEdited="userAge = $event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data: function() {
          return {
            username: 'Phemmy',
            userAge: 1
          };
        },

        methods: {
          changeName() {
            this.username = "Inioluwa"
          }
        },

        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
