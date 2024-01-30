<template>
  <div class="hello">
    <button
      class="bg-[#41B883] px-5 py-2 text-white rounded border border-transparent transition-all duration-300 hover:text-[#41B883] hover:bg-transparent hover:border-[#41B883]"
    >
      {{ title }}
    </button>
  </div>
</template>

<script>
export default { name: "MyButton", props: { title: String } };
</script>
