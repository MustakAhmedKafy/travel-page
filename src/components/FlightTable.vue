<template>
  <div class="container md:px-12 px-3 mb-8">
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
          </tr>
        </thead>
        <tbody class="text-gray-500">
          <tr
            v-for="(flight, index) in flights"
            :key="index"
            class="odd:bg-white odd:dark:bg-gray-900 even:bg-[#e5e7eb] border-blue-700"
          >
            <td class="py-2 px-4 border-b">
              <p>{{ flight.flight[0] }}</p>
              <p>{{ flight.flight[1] }}</p>
            </td>
            <td class="py-2 px-4 border-b text-center">
              <p>
                {{ flight.aircraft[0] }}
              </p>
              <p>{{ flight.aircraft[1] }}</p>
            </td>
            <td class="py-2 px-4 border-b">
              <p>{{ flight.class[0] }}</p>
              <p>{{ flight.class[1] }}</p>
            </td>
            <td class="py-2 px-4 border-b">
              <p>{{ flight.fare[0] }}</p>
              <p>{{ flight.fare[1] }}</p>
            </td>
            <td class="py-2 px-4 border-b"><p>{{ flight.route[0] }}</p> <p>{{ flight.route[1] }}</p></td>
            <td class="py-2 px-4 border-b"><p>{{ flight.departure[0] }}</p><p>{{ flight.departure[1] }}</p></td>
            <td class="py-2 px-4 border-b"><p>{{ flight.arrival[0] }}</p><p>{{ flight.arrival[1] }}</p></td>
            <td class="py-2 px-4 border-b">{{ flight.duration }}</td>
            <td class="py-2 px-4 border-b text-center">
              {{ flight.price }}
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
import { ref, onMounted } from "vue";
import axios from "axios";

const flights = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get("/data.json");
    const flightData = response.data.flightOffers || [];

    // Parse the flight data to the required format
    flights.value = flightData.map((offer) => {
      const itinerary = offer.itineraries[0] || {};
      const segments = itinerary.segments || [];

      return {
        flight: segments.map((seg) => `${seg.carrierCode}${seg.flightNumber}`),
        aircraft: segments.map((seg) => seg.aircraft || "N/A"),
        class: offer.class && offer.class[0] ? offer.class[0] : "N/A",
        fare:
          offer.fareBasis && offer.fareBasis[0] ? offer.fareBasis[0] : "N/A",
        route: segments.map(
          (seg) => `${seg.departure.iataCode}-${seg.arrival.iataCode}`
        ),
        departure: segments.map((seg) => seg.departure.at),
        arrival: segments.map((seg) => seg.arrival.at),
        duration: itinerary.duration || "N/A",
        price: offer.price || "N/A",
      };
    });
  } catch (error) {
    console.error("Error fetching flight data:", error);
  }
});
</script>

<style scoped>
td{
  border-bottom: 1px solid #f87171;
}
</style>
