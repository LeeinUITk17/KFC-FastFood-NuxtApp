<template>
  <div class="overflow-x-auto py-4 whitespace-nowrap bg-red-500 rounded-2xl z-20 ">
    <div class="flex space-x-8 justify-center">
      <div
        v-for="item in menuItems"
        :key="item.id"
        class="text-center font-bold text-lg uppercase tracking-wider flex-shrink-0"
      >
        <a
          href="#"
          :class="{'text-white': item.isActive, 'text-gray-900': !item.isActive, 'hover:text-gray-100': !item.isActive}"
          @click.prevent="handleClick(item.data)"
        >
          {{ item.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ScrollableMenu',
  props: {
    menuItems: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleClick(sectionId) {
      this.$emit('scrollToSection', sectionId);
    },
  },
};
</script>
