<template>
  <h2 class="text-2xl font-bold text-[#111827] md:ps-12 ps-6 pt-2">Master Price</h2>
  <hr class="h-px my-4 bg-gray-200 border-0 dark:bg-gray-700" />
  <div class="container mx-auto md:px-12 px-3">
    <div class="mx-auto pb-8 pt-2">
      <div class="flex space-x-2 items-center justify-center mb-4">
        <div class="inline-flex rounded-md shadow-sm" role="group">
          <button
            type="button"
            class="px-4 py-2 text-sm font-medium text-gray-900 bg-white border border-[#2e3791] hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-2 focus:ring-blue-700 focus:text-blue-700 dark:bg-gray-800 dark:border-gray-700 dark:text-white dark:hover:text-white dark:hover:bg-gray-700 dark:focus:ring-blue-500 dark:focus:text-white"
          >
            Round Trip
          </button>
          <button
            type="button"
            class="px-4 py-2 text-sm font-medium text-white bg-[#2e3791] border-t border-b border-[#2e3791] hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-2 focus:ring-blue-700 focus:text-blue-700 focus:bg-white dark:bg-gray-800 dark:border-gray-700 dark:text-white dark:hover:text-white dark:hover:bg-gray-700 dark:focus:ring-blue-500 dark:focus:text-white"
          >
            One Way
          </button>
          <button
            type="button"
            class="px-4 py-2 text-sm font-medium text-gray-900 bg-white border border-[#2e3791] hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-2 focus:ring-blue-700 focus:text-blue-700 dark:bg-gray-800 dark:border-gray-700 dark:text-white dark:hover:text-white dark:hover:bg-gray-700 dark:focus:ring-blue-500 dark:focus:text-white"
          >
            Multi City
          </button>
        </div>
      </div>
      <hr class="h-[1px] my-4 bg-[#818cf8] border-0 dark:bg-gray-700" />
      <div class="">
        <div class="grid md:grid-cols-12 grid-cols-4 gap-4 items-center mb-2">
          <!-- LHR -->
          <div class="col-span-2">
            <input
              type="text"
              placeholder="LHR"
              class="px-4 py-2 border w-full"
            />
          </div>
          <!-- CDG -->
          <div class="col-span-2">
            <input
              type="text"
              placeholder="CDG"
              class="px-4 py-2 border w-full"
            />
          </div>
          <!-- date -->
          <div class="col-span-2">
            <input
              type="date"
              value="2022-12-22"
              class="px-4 py-2 border w-full"
            />
          </div>

          <!-- day- -->
          <div class="md:col-span-1 col-span-2">
            <select class="px-4 py-2 border w-full">
              <option>Day -</option>
            </select>
          </div>
          <!-- day+ -->
          <div class="md:col-span-1 col-span-2">
            <select class="px-4 py-2 border w-full">
              <option>Day +</option>
            </select>
          </div>
          <!-- time -->
          <div class="col-span-2">
            <select class="px-4 py-2 border w-full">
              <option>Any time</option>
            </select>
          </div>
          <!-- adt -->
          <div class="md:col-span-1 col-span-2">
            <div class="flex items-center gap-1 w-full">
              <p>
                <svg
                  class="w-4 h-4 text-gray-800 dark:text-white"
                  aria-hidden="true"
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M5 12h14m-7 7V5"
                  />
                </svg>
              </p>
              <select class="px-4 py-2 border w-full">
                <option>ADT</option>
              </select>
            </div>
          </div>
          <!-- number -->
          <div class="md:col-span-1 col-span-2">
            <div class="flex items-center gap-1">
              <select class="px-4 py-2 border w-full">
                <option>1</option>
              </select>
              <p>
                <svg
                  class="w-4 h-4 text-gray-800 dark:text-white"
                  aria-hidden="true"
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M5 12h14m-7 7V5"
                  />
                </svg>
              </p>
            </div>
          </div>
        </div>

        <!-- Extra Options -->
        <div class="flex items-center justify-between my-4">
          <div>
            <input type="checkbox" id="extraOptions" class="mr-2" />
            <label for="extraOptions" class="mr-4">Extra Options</label>
          </div>

          <div>
            <label class="mr-2">Environment:</label>
            <input
              type="radio"
              name="environment"
              id="dummy"
              value="dummy"
              checked
              class="mr-1"
            />
            <label for="dummy" class="mr-4">Dummy</label>
            <input
              type="radio"
              name="environment"
              id="pdt"
              value="pdt"
              class="mr-1"
            />
            <label for="pdt">PDT</label>
          </div>

          <button class="px-6 py-2 bg-[#312e81] text-white rounded">
            Search
          </button>
        </div>
      </div>
      <hr class="h-[2px] my-4 bg-[#818cf8] border-0 dark:bg-gray-700" />
    </div>
  </div>
</template>

<script setup></script>

<style scoped></style>
