<template>
    <div>
      <div v-if="step === 1">
        <!-- Step 1: User Information -->
        <h2>Step 1: User Information</h2>
        <div>
          <label for="gender">Gender:</label>
          <select v-model="userData.gender" id="gender">
            <option value="">Select</option>
            <option value="male">Male</option>
            <option value="female">Female</option>
            <option value="other">Other</option>
          </select>
          <div v-if="errors.gender" class="error">{{ errors.gender }}</div>
        </div>
        <!-- Other fields can be added similarly -->
        <button @click="validateStep1">Next</button>
      </div>
  
      <div v-if="step === 2">
        <!-- Step 2: Account Information -->
        <h2>Step 2: Account Information</h2>
        <!-- Add fields for account information -->
        <button @click="validateStep2">Next</button>
      </div>
  
      <!-- Other steps can be added similarly -->
  
      <div v-if="step === totalSteps">
        <!-- Final step: Terms and Conditions -->
        <h2>Step {{ totalSteps }}: Terms and Conditions</h2>
        <div>
          <input type="checkbox" id="tac_accepted" v-model="userData.tacAccepted">
          <label for="tac_accepted">I accept the Terms and Conditions</label>
          <div v-if="errors.tacAccepted" class="error">{{ errors.tacAccepted }}</div>
        </div>
        <button @click="submitForm">Submit</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        step: 1,
        totalSteps: 3,
        userData: {
          gender: '',
          // Add other fields here
          tacAccepted: false
        },
        errors: {}
      };
    },
    methods: {
      validateStep1() {
        // Example validation for step 1
        this.errors = {};
        if (!this.userData.gender) {
          this.errors.gender = 'Gender is required';
          return;
        }
        // Other field validations can be added similarly
        this.step++;
      },
      // Add methods for other steps similarly
      submitForm() {
        // Handle form submission
        console.log('Form submitted:', this.userData);
      }
    }
  };
  </script>
  
  <style>
  .error {
    color: red;
  }
  </style>
  