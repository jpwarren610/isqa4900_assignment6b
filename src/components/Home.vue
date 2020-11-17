<template>
  <v-main>
    <v-container fluid>
      <v-row>
        <v-col align="center" justify="center" cols="12">
          <blockquote>
            Welcome {{validUserName}}!
            <!-- <footer>
              <small>
                <em>"BBQ may not be the road to world peace, but it's a start." Anthony Bourdain</em>
              </small>
            </footer> -->
          </blockquote>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid>
      <v-row
        align="center"
        justify="center"
      >
        <v-col 
          cols="12"
            sm="10"
            md="8"
        >
          <v-card class="elevation-2">
            <v-container
              fluid
              grid-list-md
            >
              <v-row>
                <v-col>
                  <v-card>
                    <v-img
                      <!-- :src="require('@/assets/images/cook.jpg')" height="200px"> -->
                    </v-img>
                    <v-card-actions>
                      <v-btn class="white--text" flat color="red darken-4" @click="viewCooks">View Cooks</v-btn>
                    </v-card-actions>
                  </v-card>
                </v-col>
                <v-col>
                  <v-card>
                  </v-card>
                </v-col>
                <v-col>
                  <v-card>
                  </v-card> 
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
<script>
  import router from '../router';
  export default {
    name: 'Home',
    data: () => ({
      validUserName: "Guest"
    }),
    mounted() {
      this.getUser();
    },
    methods: {
      viewCooks() {
        router.push('/cook-list');
      },
      getUser() {
        if (localStorage.getItem("isAuthenticates")
          && JSON.parse(localStorage.getItem("isAuthenticates")) === true) {
          this.validUserName = JSON.parse(localStorage.getItem("log_user"));
        }
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
