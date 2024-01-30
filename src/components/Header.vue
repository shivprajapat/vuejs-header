<!-- eslint-disable vue/require-v-for-key -->
<template>
  <nav class="bg-white border-gray-200 px-4 md:px-6 py-2.5 border-b">
    <div
      class="flex flex-wrap justify-between items-center mx-auto max-w-screen-xl"
    >
      <a href="/" class="flex items-center">
        <img
          src="../assets/logo.png"
          class="mr-3 h-6 sm:h-9"
          alt="Flowbite Logo"
        />
        <span
          class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"
          >Vue</span
        >
      </a>
      <div class="flex items-center md:order-2">
        <div class="hidden md:block">
          <Button title="Get Started" />
        </div>
        <button
          type="button"
          class="inline-flex items-center p-2 ml-3 text-sm text-white bg-[#41B883] rounded-md md:hidden"
          @click="menuOpenHandler"
        >
          {{ open ? "Close" : "Open" }}
        </button>
      </div>
      <div
        :class="[
          open ? 'flex' : 'hidden',
          'md:flex justify-between items-center w-full md:w-auto md:order-1',
        ]"
        id="mobile-menu-2"
      >
        <ul
          class="flex flex-col mt-4 font-medium md:flex-row md:space-x-8 md:mt-0 w-full"
        >
          <li v-for="link in linksData">
            <router-link
              :to="link.link"
              :active-class="'text-[#41B883]'"
              class="block py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-primary-700 md:p-0"
              >{{ link.name }}</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import { ref } from "vue";
import Button from "./Button.vue";

export default {
  name: "MyHeader",
  components: { Button },

  setup() {
    let open = ref(false);
    let linksData = [
      { name: "Home", link: "/" },
      { name: "About", link: "/about" },
      { name: "Service", link: "/service" },
      { name: "Blog", link: "/blog" },
      { name: "Contact", link: "/contact" },
    ];
    function menuOpenHandler() {
      open.value = !open.value;
      console.log("menuOpenHandler");
    }
    return { linksData, open, menuOpenHandler };
  },
};
</script>
