<template>
    <Header/>
    <div class="container mx-auto bg-white h-5/6 py-10">
      <div class=" mt-6 p-2 w-full ">
        <bookParty />
      </div>
    </div>
    <Footer/>
  </template>
  
  <script>
    
  import bookParty from '~/components/bookParty.vue';
  import Header from '~/components/header.vue';
  import Footer from '~/components/Footer.vue';
  export default {
    name: 'BookPartyPage',
    components: {
      bookParty,
        Header,
        Footer,
    },
  };
  </script>
  

  