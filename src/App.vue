<template>
  <button
    type="button"
    @click="showHide()"
    class="
      mt-2
      border-2
      rounded-md
      p-2
      bg-sky-600
      hover:bg-sky-700
      text-white
      font-semibold
    "
  >
    {{ status }}
  </button>
  <div class="min-h-screen flex justify-center items-center">
    <form
      class="border-2 rounded-lg w-[400px] h-[400px] shadow-lg shadow-gray-900"
      action=""
      v-if="show"
    >
      <div class="my-10 flex flex-col items-center">
        <h1 class="font-bolder text-4xl font-serif mb-5">Check Given Values</h1>
        <input
          type="text"
          placeholder="Enter user name"
          class="
            p-2
            border-2 border-gray-600
            rounded-lg
            w-[350px]
            focus:outline-none
            focus:ring
            focus:ring-green-500
            focus:border-white
          "
          v-model="username"
        />
        <input
          type="password"
          name="password"
          id="password"
          placeholder="Enter your Password"
          v-model="password"
          class="
            p-2
            border-2
            mt-2
            border-black
            rounded-lg
            w-[350px]
            focus:outline-none
            focus:ring
            focus:ring-green-500
            focus:border-white
          "
        />
        <button
          type="button"
          @click="getData()"
          class="
            mt-2
            border-2
            rounded-md
            p-2
            bg-sky-600
            hover:bg-sky-700
            text-white
            font-semibold
            w-[350px]
          "
        >
          CheckValue
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {
  },
  data() {
    return {
      username: null,
      password: null,
      show: true,
      status: "Hide",
    };
  },
  methods: {
    getData() {
      console.log("Data of user is : ", this.username, this.password);
    },
    showHide() {
      this.show = this.show ? false : true;
      this.status = this.show ? "Hide" : "Show";
    },
  },
};
</script>

