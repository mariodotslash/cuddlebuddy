<template>
    
    <section class="bg-amber-100 dark:bg-gray-900">
    <div class="grid max-w-screen-xl px-4 py-8 mx-auto lg:gap-8 xl:gap-0 lg:py-16 lg:grid-cols-12">
        <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
            <img src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/hero/phone-mockup.png" alt="mockup">
        </div>    
        <div class="md:ml-auto place-self-center lg:col-span-7">
            <h1 class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white">Craving Cuddles?</h1>
            <p class="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400">Register now, and find your perfect CuddleBuddy today!</p>
            

            <form @submit.prevent="submitForm" class="max-w-lg mx-auto p-4 bg-white rounded-xl mt-8">
    <!-- First name and last name inputs -->
    <div class="grid md:grid-cols-2 md:gap-6">
      <!-- First name -->
      <div class="relative z-0 w-full mb-5 group">
        <input v-model="firstName" @input="validateFirstName" type="text" name="floating_first_name" id="floating_first_name" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
        <label for="floating_first_name" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">First name</label>
        <span v-if="!firstNameValid" class="text-red-500 text-xs">Please enter a valid first name.</span>
      </div>
      <!-- Last name -->
      <div class="relative z-0 w-full mb-5 group">
        <input v-model="lastName" @input="validateLastName" type="text" name="floating_last_name" id="floating_last_name" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
        <label for="floating_last_name" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Last name</label>
        <span v-if="!lastNameValid" class="text-red-500 text-xs">Please enter a valid last name.</span>
      </div>
    </div>
    <!-- Email input and Gender dropdown -->
    <div class="grid md:grid-cols-2 md:gap-6">
      <!-- Email -->
      <div class="relative z-0 w-full mb-5 group">
        <input v-model="email" @input="validateEmail" type="email" name="floating_email" id="floating_email" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-yellow-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
        <label for="floating_email" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 rtl:peer-focus:left-auto peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Email address</label>
        <span v-if="!emailValid" class="text-red-500 text-xs">Please enter a valid email address.</span>
      </div>
      <!-- Gender dropdown -->
      <div class="relative z-0 w-full mb-5 group">
        <select v-model="gender" name="gender" id="gender" class="block py-2.5 px-0 w-full text-sm text-gray-500 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" required>
          <option value="" disabled selected>Select your gender</option>
          <option value="male">Male</option>
          <option value="female">Female</option>
          <option value="other">Other</option>
        </select>
        <label for="gender" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Gender</label>
        <span v-if="!genderValid" class="text-red-500 text-xs">Please select your gender.</span>
      </div>
    </div>
    <!-- Password inputs -->
    <div class="grid md:grid-cols-2 md:gap-6">
      <!-- Password -->
      <div class="relative z-0 w-full mb-5 group">
        <input v-model="password" @input="validatePassword" type="password" name="floating_password" id="floating_password" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
        <label for="floating_password" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Password</label>
        <span v-if="!passwordValid" class="text-red-500 text-xs">Password needs to be 6 characters.</span>
      </div>
      <!-- Confirm password -->
      <div class="relative z-0 w-full mb-5 group">
        <input v-model="confirmPassword" @input="validateConfirmPassword" type="password" name="repeat_password" id="floating_repeat_password" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
        <label for="floating_repeat_password" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Confirm password</label>
        <span v-if="!confirmPasswordValid" class="text-red-500 text-xs">Passwords do not match.</span>
      </div>
    </div>
    <!-- Checkbox for terms and conditions -->
    <div class="relative z-0 w-full mb-5 group">
      <div class="flex items-center h-5">
        <input id="terms" type="checkbox" value="" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-yellow-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-yellow-600 dark:ring-offset-gray-800 dark:focus:ring-offset-gray-800" required />
        <label for="terms" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">I agree with the <a href="#" class="text-blue-600">terms and conditions</a></label>
      </div>
    </div>
    <!-- Button to submit the form -->
    <PrimaryButton type="submit">Register</PrimaryButton>
  </form>
        </div>
                 
    </div>
</section>

<section id='about' class="bg-white dark:bg-gray-900">
    <div class="gap-16 items-center py-8 px-4 mx-auto max-w-screen-xl lg:grid lg:grid-cols-2 lg:py-16 lg:px-6">
        <div class="grid grid-cols-2 gap-4 mt-8">
            <img class="w-full rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-2.png" alt="office content 1">
            <img class="mt-4 w-full lg:mt-10 rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-1.png" alt="office content 2">
        </div>
 
        <div class="max-w-3xl mx-auto text-center mt-4 md:mt-0">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">About CuddleBuddy</h2>
            <p class="text-lg text-gray-700 leading-relaxed">
                At CuddleBuddy, we believe in the power of human connection and the importance of platonic touch.
                Our platform aims to provide a safe and welcoming space for individuals to find cuddle buddies
                and enjoy the benefits of cuddling without any romantic expectations.
            </p>
            <p class="mt-4 text-lg text-gray-700 leading-relaxed">
                Whether you're seeking companionship, stress relief, or simply craving the warmth of human touch,
                CuddleBuddy is here to facilitate meaningful connections and promote overall well-being.
            </p>
            <p class="mt-4 text-lg text-gray-700 leading-relaxed">
                Join our community today and embrace the joy of cuddling with like-minded individuals who share your
                appreciation for affectionate human interaction.
            </p>
        </div>

    </div>
</section>

<section id='services' class="bg-amber-100 dark:bg-gray-900">
    <div class="gap-16 items-center py-8 px-4 mx-auto max-w-screen-xl lg:grid lg:grid-cols-2 lg:py-16 lg:px-6">
 
        <div class="max-w-3xl mx-auto text-center">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">CuddleBuddy offers a range of services:</h2>
            <ul class="list-disc list-inside text-left space-y-2">
                <li class=""><span class="font-bold">Cuddle Matching:</span> We match individuals based on their preferences and comfort levels to ensure a mutually enjoyable cuddling experience.</li>
                <li class=""><span class="font-bold">Cuddle Events:</span> We organize group cuddle sessions in safe and comfortable environments, allowing people to connect and unwind together.</li>
                <li class=""><span class="font-bold">Professional Cuddling:</span> Our trained cuddle professionals provide one-on-one cuddling sessions tailored to each individual's needs and boundaries.</li>
                <li class=""><span class="font-bold">Workshops and Classes:</span> We offer workshops and classes on cuddling techniques, communication skills, and boundary-setting to promote healthy and consensual physical intimacy.</li>
                <li class=""><span class="font-bold">Online Community: </span>Our online platform provides a supportive community where members can share experiences, seek advice, and connect with like-minded individuals.</li>
                <li class=""><span class="font-bold">Cuddle Accessories: </span>We offer a range of cuddle accessories, such as cozy blankets, plush pillows, and soothing music playlists, to enhance the cuddling experience at home.</li>
            </ul>

        </div>

        <div class="grid grid-cols-2 gap-4 mt-8">
            <img class="w-full rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-2.png" alt="office content 1">
            <img class="mt-4 w-full lg:mt-10 rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-1.png" alt="office content 2">
        </div>

    </div>
</section>


<section id='pricing' class="bg-white dark:bg-gray-900">
  <div class="py-8 px-4 mx-auto max-w-screen-xl lg:py-16 lg:px-6">
      <div class="mx-auto max-w-screen-md text-center mb-8 lg:mb-12">
          <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white">Designed for you</h2>
          <p class="mb-5 font-light text-gray-500 sm:text-xl dark:text-gray-400">Here at CuddleBuddy we believe in the power of human connection through comforting embraces.</p>
      </div>
      <div class="space-y-8 lg:grid lg:grid-cols-3 sm:gap-6 xl:gap-10 lg:space-y-0">
          <!-- Pricing Card -->
          <Card price="R300" slogan="Beginner">Snuggle Starter</Card>
          <!-- Pricing Card -->
         <Card price="R500" slogan="Intermediate">Hug Harmony</Card>
          <!-- Pricing Card -->
         <Card price="R900" slogan="Professional">Cuddle Connoisseur</Card>
      </div>
  </div>
</section>


<section id='contact' class="bg-amber-100 dark:bg-gray-900">
    <div class="gap-16 items-center py-8 px-4 mx-auto max-w-screen-xl lg:grid lg:grid-cols-2 lg:py-16 lg:px-6">
        <div class="grid grid-cols-2 gap-4 mt-8">
            <img class="w-full rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-2.png" alt="office content 1">
            <img class="mt-4 w-full lg:mt-10 rounded-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/content/office-long-1.png" alt="office content 2">
        </div>
 
        <div class="max-w-3xl mx-auto mt-4 md:mt-0">
           
            <form class="max-w-lg mx-auto p-4 bg-white rounded-xl mt-8">
                <h2 class="text-3xl font-bold text-gray-800 mb-6">Contact us</h2>
    <!-- Name input -->
    <div class="relative z-0 w-full mb-5 group">
      <input type="text" name="contact_name" id="contact_name" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
      <label for="contact_name" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Your Name</label>
    </div>
    <!-- Email input -->
    <div class="relative z-0 w-full mb-5 group">
      <input type="email" name="contact_email" id="contact_email" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-yellow-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required />
      <label for="contact_email" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 rtl:peer-focus:left-auto peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Your Email</label>
    </div>
    <!-- Message textarea -->
    <div class="relative z-0 w-full mb-5 group">
      <textarea name="contact_message" id="contact_message" rows="4" class="block py-2.5 px-0 w-full text-sm text-gray-900 bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" " required></textarea>
      <label for="contact_message" class="peer-focus:font-medium absolute text-sm text-gray-500 dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:start-0 rtl:peer-focus:translate-x-1/4 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Your Message</label>
    </div>
    <!-- Checkbox for privacy policy -->
    <div class="relative z-0 w-full mb-5 group">
      <div class="flex items-center h-5">
        <input id="privacy_policy" type="checkbox" value="" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-yellow-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-yellow-600 dark:ring-offset-gray-800 dark:focus:ring-offset-gray-800" required />
        <label for="privacy_policy" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">I have read and agree to the <a href="#" class="text-blue-600">privacy policy</a></label>
      </div>
    </div>
    <!-- Button to submit the form -->
    <PrimaryButton type="submit">Send Message</PrimaryButton>
  </form>

        </div>

    </div>
</section>


</template>

<script setup>
import PrimaryButton from '../components/PrimaryButton.vue';

</script>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      gender: '',
      password: '',
      confirmPassword: '',
      firstNameValid: true,
      lastNameValid: true,
      emailValid: true,
      genderValid: true,
      passwordValid: true,
      confirmPasswordValid: true
    };
  },
  methods: {
    validateFirstName() {
      this.firstNameValid = /^[a-zA-Z]+$/.test(this.firstName);
    },
    validateLastName() {
      this.lastNameValid = /^[a-zA-Z]+$/.test(this.lastName);
    },
    validateEmail() {
      const pattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      this.emailValid = pattern.test(this.email);
    },
    validateGender() {
      this.genderValid = !!this.gender;
    },
    validatePassword() {
      // You can add your password validation logic here
      this.passwordValid = this.password.length >= 8;
    },
    validateConfirmPassword() {
      this.confirmPasswordValid = this.password === this.confirmPassword;
    },
    submitForm() {
      this.validateFirstName();
      this.validateLastName();
      this.validateEmail();
      this.validateGender();
      this.validatePassword();
      this.validateConfirmPassword();
      if (this.firstNameValid && this.lastNameValid && this.emailValid && this.genderValid && this.passwordValid && this.confirmPasswordValid) {
        // Form submission logic goes here
        console.log('Form submitted successfully!');
      } else {
        console.log('Form submission failed. Please check your inputs.');
      }
    }
  }
};
</script>