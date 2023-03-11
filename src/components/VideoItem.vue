<template>
  <div class="group">
    <a href="">
      <div class="relative">
        <img :src="`https://picsum.photos/seed/image${index}/720/404`" />
        <span
          class="bg-opacity-60 opacity-0 group-hover:opacity-100 absolute top-0 right-0 text-white bg-black rounded-sm m-1 p-1"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"
            />
          </svg>
        </span>
        <span
          class="bg-opacity-60 opacity-0 group-hover:opacity-100 absolute top-8 right-0 text-white bg-black rounded-sm m-1 p-1"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3.75 5.25h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5"
            />
          </svg>
        </span>
        <span
          class="duration-500 opacity-100 group-hover:opacity-0 absolute bottom-0 right-0 text-white bg-black text-xs rounded-sm m-1 p-1 font-semibold"
          >05:45</span
        >
      </div>
    </a>

    <div class="flex items-start mr-3 mt-2 mb-7">
      <img
        :src="`https://picsum.photos/seed/avatar${index}/68`"
        class="rounded-full mr-3 w-9 h-9"
      />
      <div class="text-gray-800 text-sm">
        <span class="font-semibold">Video name</span>
        <div class="mt-1 flex items-center">
          <span>Chanel name</span>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-3.5 h-3.5 ml-1"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
            />
          </svg>
        </div>
        <div>
          <span>1K views</span>
          &middot;
          <span>4 days ago</span>
        </div>
      </div>

      <button
        class="ml-auto -mt-1 p-1 opacity-0 group-hover:opacity-100 text-gray-500 hover:text-gray-700 focus:outline-none"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 6.75a.75.75 0 110-1.5.75.75 0 010 1.5zM12 12.75a.75.75 0 110-1.5.75.75 0 010 1.5zM12 18.75a.75.75 0 110-1.5.75.75 0 010 1.5z"
          />
        </svg>
      </button>
    </div>
  </div>
</template>
<script>

export default {
props:  ['index']
};
</script>