<template>
  <div class="wrapper">
    <div class="section page-header header-filter" :style="headerStyle">
      <div class="container">
        <div class="md-layout">
          <div
            class="md-layout-item md-size-33 md-small-size-66 md-xsmall-size-100 md-medium-size-40 mx-auto"
          >
            <login-card header-color="green">
              <h4 slot="title" class="card-title">Login</h4>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-facebook-square"></i>
              </md-button>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-twitter"></i>
              </md-button>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-google-plus-g"></i>
              </md-button>
              <!--<p slot="description" class="description">Or Be Classical</p>-->
              <md-field class="md-form-group" slot="inputs">
                <md-icon>face</md-icon>
                <label>First Name...</label>
                <md-input v-model="firstname"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>email</md-icon>
                <label>Email...</label>
                <md-input v-model="email" type="email"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>lock_outline</md-icon>
                <label>Password...</label>
                <md-input v-model="password"></md-input>
              </md-field>
              <md-button slot="footer" class="md-simple md-success md-lg" v-on:click="login">
                Get Started
              </md-button>
            </login-card>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { LoginCard } from "@/components";
import axios from 'axios'

//const superagent = require('superagent');

export default {
  components: {
    LoginCard
  },
  bodyClass: "login-page",
  data() {
    return {
      firstname: null,
      email: null,
      password: null
    };
  },
    methods: {
        login: function (event) {
            // `this` inside methods points to the Vue instance
            alert('Hello ' + this.name + '!');
            var config = {
              headers: {'Authorization': 'Bearer BQDSwcL68XxrizzYZQApxdCfxDDk6-2_tX_0T6Ht1Gbb0s9nAkOsPeSdM9_XwWz9j7o2VrgKqeTA0gA8KlN6fLAI-WHEs-RncQK97zhpiuFJ1YNKyb2ZYcx0k324VQPLt6JhWkW1GqJ786iASMar7tQ_15Mm5noWmA"'}
            }
            axios.get('	https://api.spotify.com/v1/browse/categories', config)
      //       console.log(superagent)
      //       superagent.get('www.google.com')
      //       superagent.get('https://api.spotify.com/v1/browse/categories')
      // .query('country=SE&locale=sv_SE&limit=10&offset=5')
      // .set('Authorization', 'Bearer BQDSwcL68XxrizzYZQApxdCfxDDk6-2_tX_0T6Ht1Gbb0s9nAkOsPeSdM9_XwWz9j7o2VrgKqeTA0gA8KlN6fLAI-WHEs-RncQK97zhpiuFJ1YNKyb2ZYcx0k324VQPLt6JhWkW1GqJ786iASMar7tQ_15Mm5noWmA');
        }
    },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/profile_city.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="css"></style>
