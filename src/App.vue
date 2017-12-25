<template>
    <div class="container">
      <div class="row text-center">
        <button @click="isSelected='signUp'"
            class="btn btn-primary">Sign Up</button>
        <button @click="isSelected='fileAComplaint'"
            class="btn btn-primary">File a Complaint</button>
      </div>
      <app-complaint v-if="isSelected=='fileAComplaint'"></app-complaint>
      <app-sign-up v-if="isSelected=='signUp'"></app-sign-up>
    </div>
</template>

<script>
    import Complaint from './Complaint.vue';
    import SignUp from './SignUp.vue';

    export default{
      data: function(){
        return {
          isSelected:"fileAComplaint",
        }
      },
      components: {
        appComplaint: Complaint,
        appSignUp: SignUp,
      }
    }


</script>

<style>
  .btn {
    margin: 10px;
  }
</style>
