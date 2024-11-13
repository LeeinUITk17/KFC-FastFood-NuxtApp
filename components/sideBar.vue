<template>
  <div>
    <div 
      class="fixed inset-0 bg-black bg-opacity-50 z-40"
      v-if="isOpen"
      @click="toggleSidebar"
    ></div>
    <div 
      class="fixed top-0 left-0 w-2/6 h-full bg-white z-50 transform transition-transform duration-300 ease-in-out"
      :class="isOpen ? 'translate-x-0' : '-translate-x-full'"
    >
      <div class="p-8 flex justify-between items-center bg-red-600 text-white">
        <button @click="toggleSidebar" class="text-2xl">&times;</button>
      </div>

      <ul class="mt-4">
        <li v-for="item in navdata" :key="item.name" class="p-4 border-b flex items-center space-x-2 hover:bg-gray-100">
          <NuxtLink :to="item.link" class="text-gray-700 p-2"><i :class="item.icon"></i>   {{ item.name }}</NuxtLink>
        </li>
      </ul>
    </div>
    <button
      class="fixed top-4 left-4 bg-red-600 font-bold text-white text-2xl px-4 py-4 rounded-2xl z-50"
      @click="toggleSidebar"
    >
      ☰ Menu
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      navdata: [
        { name: 'Home', link: '/', icon: 'fas fa-home fa-2x' },
        { name: 'Booking a party', link: '/booking', icon: 'fas fa-calendar-alt fa-2x' },
        { name: 'Find DC store', link: '/findkfc', icon: 'fas fa-map-marker-alt fa-2x' },
        { name: 'Your Profile', link: '/profile/detail', icon: 'fas fa-user fa-2x' },
        { name: 'Log In', link: '/signIn', icon: 'fas fa-sign-in-alt fa-2x' },
      ],
    };
  },
  methods: {
    toggleSidebar() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>
