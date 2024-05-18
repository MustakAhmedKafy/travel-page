<template>
  <div>
    <Header />
    <!-- form -->
    <Search />
    <FlightTable/>
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Search from "./components/Search.vue";
import FlightTable from "./components/FlightTable.vue";
</script>

<style scoped></style>
