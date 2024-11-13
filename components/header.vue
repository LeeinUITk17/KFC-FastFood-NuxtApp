<template>
    <header class="bg-red-600 text-white py-4">
      <div class="container mx-auto flex items-center justify-between">
        <div class="flex items-center space-x-4">
        <p class="text-4xl font-bold text-bisque mr-4">Drunken Clam</p>
          <img
            src="https://res.cloudinary.com/dbonwxmgl/image/upload/v1731220914/d5gjgrzdoft32wmaxlmy.png"
            alt="KFC Logo"
            class="h-16"
          />
          <nav class="hidden lg:flex text-gray-700 text-xl space-x-6">
            <headerItem title="Home" link="/" :activeLink="currentPath" />
            <headerItem title="Booking A Party" link="/booking" :activeLink="currentPath" />
            <headerItem title="Find DC Store" link="/findkfc" :activeLink="currentPath" />
          </nav>
        </div>
        <div class="flex items-center space-x-4">
          <div class="relative">
            <div
              @click="toggleLanguage"
              role="switch"
              :aria-checked="selectedLanguage === 'VN'"
              class="w-16 h-8 bg-red-500 rounded-full flex items-center cursor-pointer relative transition-all duration-300"
              :class="{'bg-green-500': selectedLanguage === 'VN'}"
            >
              <div
                class="w-8 h-8 bg-green-600 rounded-full shadow-md transition-transform duration-300 transform"
                :class="{'translate-x-full': selectedLanguage === 'VN'}"
              ></div>
              <div class="absolute inset-0 flex justify-between px-2 text-xs py-2 font-bold">
                <span :class="{'text-white': selectedLanguage === 'VN'}">EN</span>
                <span :class="{'text-white': selectedLanguage === 'EN'}">VN</span>
              </div>
            </div>
          </div>
          <nuxt-link to="/cart" class="hover:text-gray-200 relative" aria-label="Cart">
            <img
              src="https://res.cloudinary.com/dbonwxmgl/image/upload/v1730812260/z6rutifjregmcrcjuecx.png"
              alt="Cart"
              class="h-8 w-8"
            />
            <span
              class="absolute top-0 right-0 bg-white text-red-600 rounded-full text-xs w-3 h-3 flex items-center justify-center"
            >
              3
            </span>
          </nuxt-link>
          <nuxt-link to="/profile/detail" class="hover:text-gray-200" aria-label="Profile">
            <img
              src="https://res.cloudinary.com/dbonwxmgl/image/upload/v1730812166/pgvlfot3advrc9kheorc.png"
              alt="Profile"
              class="h-8 w-8"
            />
          </nuxt-link>
          <sideBar />
        </div>
      </div>
    </header>
  </template>
  
  <script>
  import sideBar from './sideBar.vue';
  import headerItem from './headerItem.vue';
  export default {
    components: {
      sideBar,
      headerItem,
    },
    data() {
      return {
        sidebarOpen: false,
        selectedLanguage: "EN",
      };
    },
    computed: {
      currentPath() {
        return this.$route.path;
      }
    },
    methods: {
      toggleDropdown(dropdown) {
        this[dropdown] = !this[dropdown];
      },
      toggleLanguage() {
        this.selectedLanguage = this.selectedLanguage === "EN" ? "VN" : "EN";
      },
    },
  };
  </script>
  
  <style scoped>
  .container {
    max-width: 1280px;
    margin: 0 auto;
    padding-left: 1rem;
    padding-right: 1rem;
  }
  
  /* Transition for smoother sliding effect */
  .w-16 {
    transition: background-color 0.3s ease-in-out;
  }
  
  .w-8 {
    transition: transform 0.3s ease-in-out;
  }
  </style>
  