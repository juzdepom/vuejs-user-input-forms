<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                  <h1>Sign Up</h1>
                  <hr>
                  <div class="form-group">
                      <label for="firstName">First Name</label>
                      <input
                              type="text"
                              id="firstName"
                              class="form-control"
                              v-model="firstName"
                              >

                  </div>
                  <div class="form-group">
                      <label for="lastName">Last Name</label>
                      <input
                              type="text"
                              id="lastName"
                              class="form-control"
                              v-model="lastName"
                              >

                  </div>
                  <div class="form-group">
                      <label for="password">Password</label>
                      <input
                              type="password"
                              id="password"
                              class="form-control"
                              v-model.lazy="password"
                              >
                  </div>
                  <div class="form-group">
                      <label for="mail">Mail</label>
                      <input
                              type="text"
                              id="mail"
                              class="form-control"
                              v-model="mail"
                              >
                  </div>
                  <div class="form-group">
                    <p>
                      <strong>Store in Database?</strong>
                    </p>
                      <label for="yes">
                          <input
                                  type="radio"
                                  id="yes"
                                  value="Yes"
                                  v-model="storeData"
                                  > Yes
                      </label>
                      <label for="no">
                          <input
                                  style="margin-left:20px;"
                                  type="radio"
                                  id="no"
                                  value="No"
                                  v-model="storeData"
                                  > No
                      </label>
                  </div>

                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- JULIA STOPPED HERE: NEXT DO BELOW  -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
            <div class="text-center">
              <button class="btn btn-primary"
                      @click.prevent="submitted">Submit</button>
            </div>

        </form>
        <hr>
        <div v-if="isSubmitted" class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{fullName}}</p>
                        <p>Mail: {{mail}}</p>
                        <p>Password: {{password}}</p>
                        <p>Store in Database? {{storeData}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      data: function(){
        return {
          firstName: '',
          lastName: '',
          password: '',
          mail: '',
          storeData: '',
          isSubmitted: false,
        }
      },
      computed: {
        fullName: function(){
          console.log('working')
          return (this.firstName + ' ' + this.lastName)
        }
      },
      methods: {
        submitted(){
          this.isSubmitted = true;
        }
      }
    }
</script>

<style>
</style>
