<template>
  <div class="container">
    <h1 class="is-size-3 has-text-centered is-uppercase">client registration form</h1>
    <form class="form">
      <div class="columns is-multiline">
        <div class="column is-3">
          <b-field label="Name">
            <b-input type="text" v-model="name" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Address">
            <b-input type="text" v-model="address" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Phone Number">
            <b-input type="text" v-model="phonenumber" maxlength="20" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Email Id">
            <b-input type="text" v-model="emailid" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>

        <div class="column is-3">
          <b-field label="Password">
            <b-input type="password" v-model="password" maxlength="6" style="width:100%" required></b-input>
          </b-field>
        </div>
      </div>
      <b-button tag="input" native-type="submit" value="Submit" />
      <b-button tag="input" native-type="reset" value="Reset" />
    </form>
  </div>
</template>

<script>
import { mapState, mapActions, mapGetters } from "vuex";
export default {
  

  data() {
    return {
      name: "",
      address: "",
      phonenumber: "",
      emailid: "",
      password: "",
      error: null
    };
  },
  methods: {
    onSubmit() {
      var request = {
        Name: this.name,
        address: this.address,
        phonenumber: this.phonenumber,
        emailid: this.emailid,
        password: this.password

      };
      
      console.log(request);
    }
  }
};
</script>