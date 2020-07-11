<template>
  <div>
    <!-- <p>First Name: {{ $route.params.firstName }}</p>
    <p>Last Name {{ $route.params.lastName }}</p> -->
    <p>First Name: {{ firstName }}</p>
    <p>Last Name {{ lastName }}</p>
  </div>
</template>

<script>
export default {
  props: ["firstName", "lastName"],
  name: "UserDetails",
};
</script>
