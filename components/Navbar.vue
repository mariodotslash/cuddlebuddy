
import PrimaryButton from './PrimaryButton.vue';
<template>
<nav class="sticky top-0 z-10 bg-slate-50 backdrop-filter backdrop-blur-lg bg-opacity-30 border-b border-gray-200">
  <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
   
    <a href="https://flowbite.com/" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="https://flowbite.com/docs/images/logo.svg" class="h-8" alt="Flowbite Logo" />
        <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">CuddleBuddy</span>
    </a>
    <Timer/>
    <button data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-default" aria-expanded="false">
        <span class="sr-only">Open main menu</span>
        <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
        </svg>
    </button>
    <div class="hidden w-full md:block md:w-auto " id="navbar-default">
      <ul class="items-center font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
        <li>
          <a href="#about" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">About</a>
        </li>
        <li>
          <a href="#services" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Services</a>
        </li>
        <li>
          <a href="#pricing" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Pricing</a>
        </li>
        <li>
          <a href="#contact" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Contact</a>
        </li>
        <li class="pt-2">
          <PrimaryButton>Login</PrimaryButton>
        </li>
      </ul>
    </div>
  </div>
</nav>

  </template>

  <!-- <template>
    <header class="bg-gray-800 text-white p-4 flex justify-between items-center">
      <div id="countdown">{{ countdown }}</div>
      <button @click="login" class="bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-4 rounded">Login</button>
    </header>
  </template>
  
  <script>
  export default {
    data() {
      return {
        countdown: '2:00', // Initial countdown time
        duration: 2 * 60, // Duration in seconds (5 minutes)
        intervalId: null // Interval ID for countdown
      };
    },
    mounted() {
      this.intervalId = setInterval(this.updateCountdown, 1000);
    },
    methods: {
      updateCountdown() {
        const minutes = Math.floor(this.duration / 60);
        const seconds = this.duration % 60;
        this.countdown = `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
  
        if (minutes === 0 && seconds < 60) {
          this.$refs.countdown.style.color = seconds % 2 === 0 ? 'red' : 'white';
        }
  
        if (this.duration === 0) {
          clearInterval(this.intervalId);
          this.countdown = "Time's up!";
        } else {
          this.duration--;
        }
      },
      login() {
        // Add your login logic here
        alert('Login clicked!');
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add Tailwind CSS classes as needed */
  </style>
   -->