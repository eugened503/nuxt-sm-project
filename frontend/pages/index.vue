<template>
  <div>
    <p>{{ message }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      message: null
    };
  },
  async mounted() {
    try {
      const response = await axios.get("http://localhost:1337/hellos/me");
      this.message = response.data;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>
