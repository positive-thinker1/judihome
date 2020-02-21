<template>
  <div>
    <div style="background-image: url('/court.png');" class="loginform is-clearfix"> 

<div id="login">
  <div class="login-card">

    <div class="card-title">
      <h1>Please Sign In</h1>
    </div>

    <div class="content">
      <form @submit.prevent="onSubmit">

       <b-field label="username">
        <b-input type="text" v-model="username" maxlength="255" style="width:300px" required></b-input>
      </b-field>
       <b-field label="password">
        <b-input
          type="password"
          v-model="password"
          minlength="6"
          style="width:300px"
          password-reveal
        ></b-input>
      </b-field>
     <b-field label="Usertype">
            <b-select v-model="usertype" placeholder="Select a login" >
                <option value="admin">Lawyer login</option>
                <option value="local">Client login</option>
            </b-select>
          </b-field>
        
        <div class="level options">
          <div class="checkbox level-left">
            <input type="checkbox" id="checkbox" class="regular-checkbox">
            <label for="checkbox"></label>
            <span>Remember me</span>
          </div>

          <a class="btn btn-link level-right" href="#">Forgot Password?</a>
        </div>
         <div v-if="apiError" class="error">{{apiError.message}}</div>
        <button type="submit" class="btn btn-primary">Login</button>
      </form>
    </div>
  </div>
</div>
      <!-- <form @submit.prevent="onSubmit">
        <b-field label="phonenumber">
          <b-input type="text" v-model="phonenumber" maxlength="255" style="width:300px" required></b-input>
        </b-field>
        <b-field label="password">
          <b-input
            type="password"
            v-model="password"
            minlength="6"
            style="width:300px"
            password-reveal
          ></b-input>
        </b-field>
        <span v-if="error !=null">{{error}}</span>
        <b-button native-type="submit" type="is-info">Login</b-button>
      </form> -->
    </div>
  </div>
</template>
<script>
import { mapState, mapActions, mapGetters } from "vuex";
export default {
  layout:"menus",
  middleware: "guest",
  data() {
    return {
      usertype: 'local',
      username: "",
      password: "",
      errorMsg: null
    };
  },
  computed: {
    ...mapState({
      apiError: state => state.MODULE_AUTH.data
    })
  },
  methods: {
    ...mapActions({
      ACTION_LOADING: "MODULE_LOADING/ACTION_LOADING",
      ACTION_USER_AUTH: "MODULE_AUTH/ACTION_USER_AUTH"
    }),
    async onSubmit() {
      let context = this;
      context.ACTION_LOADING(true);
      try {
        let formData = new FormData();
        formData.append("email",context.username)
        formData.append("password",context.password)
        var request = {
          usertype:context.usertype,
          requestData:{
            data: formData
          }
        };
        var result = await context.ACTION_USER_AUTH(request);
      } catch (error) {
        return context.$nuxt.error({ statusCode: 500, message: error });
      } finally {
        context.ACTION_LOADING(false);
      }
    }
  }
};
</script>


  