<template>
  <div class="container md:px-12 px-6">
    <div class="overflow-x-auto">
      <table class="min-w-full bg-white">
        <thead class="text-gray-500 bg-[#e5e7eb]">
          <tr>
            <th class="py-2 px-4 border-b">FLIGHT</th>
            <th class="py-2 px-4 border-b">AIRCRAFT</th>
            <th class="py-2 px-4 border-b">CLASS</th>
            <th class="py-2 px-4 border-b">FARE</th>
            <th class="py-2 px-4 border-b">ROUTE</th>
            <th class="py-2 px-4 border-b">DEPARTURE</th>
            <th class="py-2 px-4 border-b">ARRIVAL</th>
            <th class="py-2 px-4 border-b">DURATION</th>
            <th class="py-2 px-4 border-b">PRICE</th>
            <th class="py-2 px-4 border-b"></th>
          </tr>
        </thead>
        <tbody class="text-gray-500">
          <tr
            v-for="(flight, index) in flights"
            :key="index"
            class="odd:bg-white odd:dark:bg-gray-900 even:bg-[#e5e7eb] border-blue-700"
          >
            <td class="py-2 px-4 border-b">{{ flight.flight }}</td>
            <td class="py-2 px-4 border-b">{{ flight.aircraft }}</td>
            <td class="py-2 px-4 border-b">{{ flight.class }}</td>
            <td class="py-2 px-4 border-b">{{ flight.fare }}</td>
            <td class="py-2 px-4 border-b">{{ flight.route }}</td>
            <td class="py-2 px-4 border-b">{{ flight.departure }}</td>
            <td class="py-2 px-4 border-b">{{ flight.arrival }}</td>
            <td class="py-2 px-4 border-b">{{ flight.duration }}</td>
            <td class="py-2 px-4 border-b">{{ flight.price }}</td>
            <td class="py-2 px-4 border-b">
              <button class="bg-[#312e81] text-white py-1 px-3 rounded">
                SELECT
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const flights = ref([
  {
    flight: "TK 333",
    aircraft: "723",
    class: "E",
    fare: "EF1PXOW",
    route: "DAC - IST",
    departure: "2022-11-22T23:30:00",
    arrival: "2022-11-23T05:40:00",
    duration: "19H 00M",
    price: "632.30",
  },
  {
    flight: "TK 73H",
    aircraft: "1865",
    class: "E",
    fare: "EF1PXOW",
    route: "IST - FCO",
    departure: "2022-11-23T12:55:00",
    arrival: "2022-11-23T13:30:00",
    duration: "19H 25M",
    price: "632.30",
  },
  {
    flight: "TK 333",
    aircraft: "713",
    class: "E",
    fare: "EF1PXOW",
    route: "DAC - IST",
    departure: "2022-11-22T06:55:00",
    arrival: "2022-11-22T12:55:00",
    duration: "19H 25M",
    price: "632.30",
  },
  {
    flight: "TK 73H",
    aircraft: "1361",
    class: "E",
    fare: "EF1PXOW",
    route: "IST - FCO",
    departure: "2022-11-22T20:30:00",
    arrival: "2022-11-22T21:20:00",
    duration: "19H 25M",
    price: "632.30",
  },
]);
</script>

<style scoped>
/* Add custom styles here if needed */
</style>
