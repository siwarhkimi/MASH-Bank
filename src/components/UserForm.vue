<template>
  <div>
    <md-toolbar class="md-primary">
      <h3 class="md-title">Enter Your Details</h3>  
    </md-toolbar>
    <md-steppers :md-active-step.sync="active" md-linear>
      <md-step id="first" md-label="First Step" :md-done.sync="first">
        <md-field :class="messageClass">
          <label>First Name</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">First Name</span>
        </md-field>
        <md-field :class="messageClass">
          <label>Last Name</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">Last Name</span>
        </md-field>
        <md-field :class="messageClass">
          <label>Username</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">Username</span>
        </md-field>
        <md-button class="md-raised md-primary" @click="setDone('first', 'second')">Continue</md-button>
      </md-step>

      <md-step
        id="second"
        md-label="Second Step"
        :md-error="secondStepError"
        :md-done.sync="second"
      >
        <md-field :class="messageClass">
          <label>Occupation</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">Occupation</span>
        </md-field>
        <md-field :class="messageClass">
          <label>State</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">state</span>
        </md-field>
        <md-field :class="messageClass">
          <label>City</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">City</span>
        </md-field>
        <md-field :class="messageClass">
          <label>Zip Code</label>
          <md-input v-model="required" required></md-input>
          <span class="md-error">Zip Code</span>
        </md-field>
        <md-button class="md-raised md-primary" @click="setDone('second', 'third')">Continue</md-button>
        <md-button class="md-raised md-primary" @click="setDone('second', 'first')">Back</md-button>
      </md-step>

      <md-step id="third" md-label="Third Step" :md-done.sync="third">
        <h4>Informations you want it to be shown in your profile</h4>
        <md-switch v-model="array" value="Username">Username</md-switch>
        <md-switch v-model="array" value="Occupation">Occupation</md-switch>
        <md-switch v-model="array" value="State">State</md-switch>
        <md-switch v-model="array" value="City">City</md-switch>
        <md-switch v-model="array" value="ZipCode">Zip Code</md-switch>
        <router-link to="/profile">
          <md-button class="md-raised md-primary" @click="setDone('third')">Done</md-button>
        </router-link>
        <md-button class="md-raised md-primary" @click="setDone('third', 'second')">Back</md-button>
      </md-step>
    </md-steppers>
  </div>
</template>

<script>
export default {
  name: "UserForm",
  data: () => ({
    active: "first",
    first: false,
    second: false,
    third: false,
    secondStepError: null,
    required: null,
    array: [],
  }),
  computed: {
    messageClass() {
      return {
        "md-invalid": this.hasMessages
      };
    }
  },
  methods: {
    setDone(id, index) {
      this[id] = true;

      this.secondStepError = null;

      if (index) {
        this.active = index;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.md-toolbar + .md-toolbar {
  margin-top: 16px;
}
h3 {
  text-align: center;
}
.md-switch {
  display: flex;
}

table {
  width: 100%;
  table-layout: fixed;
}
th {
  text-align: left;
}
</style>

