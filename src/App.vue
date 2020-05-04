<template>
  <div class="container">
    <form v-if="!isSubmitted">
      <div class="row">
        <div
          class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3"
        >
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->

          <appFullName v-model="userData.fullName"></appFullName>

          <div class="form-gorup">
            <label for="email">
              <input
                type="text"
                class="form-control"
                v-model="userData.email"
              />Mail</label
            >
          </div>
          <div class="form-gorup">
            <label for="password">
              <input
                type="password"
                class="form-control"
                v-model="userData.password"
              />Password</label
            >
          </div>
          <div class="form-gorup">
            <label for="storeData">
              <appSwitch v-model="storeData"></appSwitch>
              Store Data?</label
            >
          </div>
          <hr />
          <button
            class="btn btn-primary"
            @click.prevent="isSubmitted = !isSubmitted"
          >
            Submit!
          </button>
          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <div class="row" v-if="isSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.fullName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>
            <p>Store in Database? : {{ storeData ? "Yes" : "No" }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Switch from "./Switch";
import FullName from "./FullName";

export default {
  data() {
    return {
      userData: {
        fullName: "Paw tak",
        email: "",
        password: ""
      },
      storeData: true,
      isSubmitted: false
    };
  },
  components: {
    appSwitch: Switch,
    appFullName: FullName
  }
};
</script>

<style></style>
