<template>
  <div class="container">
    <h1 class="is-size-3 has-text-centered is-uppercase">Criminal Case form</h1>
    <form>
      <div class="columns is-multiline">
        <div class="column is-3">
          <b-field label="Party Name">
            <b-input type="text" v-model=" partyname" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Party Father'sName">
            <b-input
              type="text"
              v-model="Partyfatherame"
              maxlength="255"
              style="width:100%"
              required
            ></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Age">
            <b-input type="number" v-model="age" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Address">
            <b-input type="text" v-model="address" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Phone Number">
            <b-input type="text" v-model="phonenumber" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Party Name">
            <b-input type="text" v-model=" partyname" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Party Father'sName">
            <b-input
              type="text"
              v-model="Partyfatherame"
              maxlength="255"
              style="width:100%"
              required
            ></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Age">
            <b-input type="number" v-model="age" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Address">
            <b-input type="text" v-model="address" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Phone Number">
            <b-input type="text" v-model="phonenumber" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Place of Occurence">
            <b-input
              type="text"
              v-model="placeofoccurence"
              maxlength="255"
              style="width:100%"
              required
            ></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="History of Case">
            <b-input
              type="text"
              v-model="historyofcase"
              maxlength="255"
              style="width:100%"
              required
            ></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="FIR Copy">
            <b-input type="text" v-model="fircopy" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Evidence">
            <b-input type="text" v-model="evidence" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Decision">
            <b-select placeholder="Select a Decision">
              <option value="1">File Case</option>
              <option value="2">Only Consult</option>
            </b-select>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Previously Involved In any Case">
            <b-select placeholder="Select a Case">
              <option value="1">Yes</option>
              <option value="2">No</option>
            </b-select>
          </b-field>
          <b-input type="text" placeholder="if yes"></b-input>
        </div>
        <div class="column is-3">
          <b-field label="Whether Need Exprienced Lawyers">
            <b-select placeholder="Select a lawyer">
              <option value="1">Yes</option>
              <option value="2">No</option>
            </b-select>
          </b-field>
        </div>
      </div>

      <b-button tag="input" native-type="submit" value="Submit" />
    </form>
  </div>
</template>
<script>
import { mapState, mapActions, mapGetters } from "vuex";
export default {
    middleware: ["auth"],
  data() {
    return {
      partyname: "",
      partyfathersname: "",
      age: "",

      address: "",
      phonenumber: "",
      opponentname: "",
      opponentfathersname: "",
      age: "",

      address: "",
      phonenumber: "",
      placeofoccurence: "",
      historyofcase: "",
      fircopy: "",
      evidence: "",
      decision: "",
      previouslyinvolvedinanycase: "",
      whetherneedexpriencedlawyers: "",
      error: null
    };
  },
  methods: {
    onSubmit() {
      var request = {
        partyname: this.partyname,
        partyfathersname: this.partyfathersname,
        age: this.age,

        address: this.address,
        phonenumber: this.phonenumber,
        opponentname: this.opponentname,
        opponentfathersname: this.opponentfathersname,
        age: this.age,

        address: this.address,
        phonenumber: this.phonenumber,

        historyofcase: this.historyofcase,
        relateddocuments: this.relateddocuments,

        decision: this.decision,

        whetherneedexpriencedlawyers: this.whetherneedexpriencedlawyers
      };

      console.log(request);
    }
  }
};
</script>


