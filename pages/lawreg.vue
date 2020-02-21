<template>
  <div class="container">
    <h1 class="is-size-3 has-text-centered is-uppercase">lawyer registration form</h1>
    <form class="form">
      <div class="columns is-multiline">
        <div class="column is-3">
          <b-field label="Name">
            <b-input type="text" v-model="name" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Age">
            <b-input type="number" v-model="age" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Gender">
            <b-select placeholder="Select a Gender">
              <option value="1">Male</option>
              <option value="2">Female</option>
              <option value="3">Others</option>
            </b-select>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Qualification">
            <b-input
              type="text"
              v-model="qualification"
              maxlength="255"
              style="width:100%"
              required
            ></b-input>
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
          <b-field label="Email Id">
            <b-input type="text" v-model="emailid" maxlength="255" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Password">
            <b-input type="password" v-model="password" maxlength="6" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Working Status">
            <b-select placeholder="Select a Working Status">
              <option value="1">Individual</option>
              <option value="2">Firm</option>
            </b-select>
          </b-field>
          <b-input type="text" placeholder="firm name"></b-input>
        </div>
        <div class="column is-3">
          <b-field label="Exprience">
            <b-input type="text" v-model="experience" maxlength="20" style="width:100%" required></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="Bar Council Enrolment Number ">
            <b-input
              type="text"
              v-model="barcouncilenrolmentnumber"
              maxlength="20"
              style="width:85%"
              required
            ></b-input>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label="certificates upload">
            <b-field class="file">
              <b-upload v-model="file">
                <a class="button">
                  <b-icon icon="upload"></b-icon>
                  <span>Click to upload</span>
                </a>
              </b-upload>
              <span class="file-name" v-if="file">{{ file.name }}</span>
            </b-field>
          </b-field>
        </div>
        <div class="column is-3">
          <b-field label=" photo upload ">
            <b-field class="photo">
              <b-upload v-model="photo">
                <a class="button">
                  <b-icon icon="upload"></b-icon>
                  <span>Click to upload</span>
                </a>
              </b-upload>
              <span class="file-name" v-if="photo">{{ file.name }}</span>
            </b-field>
          </b-field>
        </div>
      </div>

      <b-button tag="input" native-type="submit" value="Submit" />
      <b-button tag="input" native-type="reset" value="Reset" />
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      age: "",
      Gender: "",
      qualification: "",
      
      address: "",
      phonenumber: "",
      emailid: "",
      password: "",
      Workingstatus: "",
      experience: "",
      barcouncilenrolmentnumber: "",
      certificatesupload: "",
      photoupload: "",
      error: null
    };
  },
  methods: {
    onSubmit() {
      var request = {
        Name: this.name,
        age: this.age,
        Gender: this.Gender,
        qualification: this.qualification,

        address: this.address,
        phonenumber: this.phonenumber,
        emailid: this.emailid,
        password: this.password,
        Workingstatus: this.Workingstatus,
        experience: this.experience,
        barcouncilenrolmentnumber: this.barcouncilenrolmentnumber,
        certificatesupload: this.certificatesupload,
        photoupload: this.photoupload
      };

      console.log(request);
    }
  }
};
</script>
