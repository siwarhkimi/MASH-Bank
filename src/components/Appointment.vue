<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary">
        <span class="md-title">MY DASHBORD</span>
        <span class="space"></span>
        <span class="md-mail">E-mail</span>
      </md-app-toolbar>

      <md-app-drawer md-permanent="clipped">
        <md-list>
          <md-list-item>
            <md-icon>account_box</md-icon>
            <router-link to="/profile">
              <span class="md-list-item-text">Profile informations</span>
            </router-link>
          </md-list-item>

          <md-list-item>
            <md-icon>exposure</md-icon>
            <router-link to="/simulator">
              <span class="md-list-item-text">Simulator</span>
            </router-link>
          </md-list-item>

          <md-list-item>
            <md-icon>today</md-icon>
            <router-link to="/appointment">
              <span class="md-list-item-text">Make an appointment</span>
            </router-link>
          </md-list-item>

          <md-list-item>
            <md-icon>alarm</md-icon>
            <router-link to="/scheduled">
              <span class="md-list-item-text">My scheduled appointments</span>
            </router-link>
          </md-list-item>
        </md-list>
      </md-app-drawer>
      <md-app-content>
        <div class="personal">
          <h2>Make an Appointment</h2>
          <hr class="solid" />
          <div class="md-layout md-gutter">
            <div class="md-layout-item">
              <md-field>
                <md-input v-model="date" class="styleInput" type="date"></md-input>
              </md-field>
            </div>
            <br />
            <div class="md-layout-item">
              <md-field>
                <label for="time">Time</label>
                <md-select v-model="time" name="time" id="time" class="styleInput">
                  <md-option value="08to10">08:00 AM - 10:00 AM</md-option>
                  <md-option value="10to12">10:00 AM - 12:00 AM</md-option>
                  <md-option value="02to04">02:00 PM - 04:00 PM</md-option>
                  <md-option value="04to06">04:00 PM - 06:00 PM</md-option>
                </md-select>
              </md-field>
            </div>
            <br />
            <div class="md-layout-item">
              <md-field>
                <label for="place">Place</label>
                <md-select v-model="place" name="place" id="place" class="styleInput">
                  <md-option value="ariana">Ariana</md-option>
                  <md-option value="tunis">Tunis</md-option>
                  <md-option value="ben arous">Ben Arous</md-option>
                  <md-option value="mahdia">Mahdia</md-option>
                  <md-option value="sousse">Sousse</md-option>
                </md-select>
              </md-field>
            </div>
          </div>
          <router-link to = "/processed">
          <md-button class="md-primary md-raised" @click="loanType = 'Car'">Submit</md-button>
          </router-link>
        </div>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
export default {
  name: "Appointment"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.personal {
  border: 2px solid black;
  height: 100%;
  text-align: center;
  margin: 3%;
  padding: 1%;
}
.md-layout-item {
  display: block;
}
  .md-app {
    min-height: 350px;
    border: 1px solid rgba(#000, .12);
  }

  .md-drawer {
    width: 230px;
    max-width: calc(100vw - 125px);
  }
  .md-mail {
    margin-left: 80%;
    font-size: 25px;
  }
</style>
