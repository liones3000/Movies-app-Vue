<template>
  <div></div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Notification",
  computed: {
    ...mapGetters(["messagePool"])
  },
  watch: {
    messagePool: "showNotification"
  },
  methods: {
    showNotification({
      variant = "warning",
      msg = "Body message",
      title = "Title alert"
    }) {
      this.$bvToast.toast(msg, {
        title,
        variant,
        solid: true
      });
    }
  }
};
</script>
