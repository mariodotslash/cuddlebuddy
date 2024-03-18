<template>
    <div :class="timerClass" class="text-black rounded-full p-2">
      <p>{{ displayTime }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        time: 300, // 5 minutes in seconds
      };
    },
    computed: {
      displayTime() {
        const minutes = Math.floor(this.time / 60);
        const seconds = this.time % 60;
        return `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
      },
      timerClass() {
        return {
          'bg-red-500 text-white animate-pulse': this.time <= 59, // Change background to red when less than or equal to 1 minute
          'bg-green-500 ': this.time > 0, // Keep background transparent when timer is running
        };
      },
    },
    mounted() {
      this.timer = setInterval(() => {
        if (this.time > 0) {
          this.time--;
        } else {
          clearInterval(this.timer); // Stop the timer when it reaches 0:00
        }
      }, 1000);
    },
    beforeDestroy() {
      clearInterval(this.timer); // Clean up timer when component is destroyed
    },
  };
  </script>
  