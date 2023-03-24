<template>
  <aside
    class="hidden xl:block w-64 max-h-screen overflow-auto fixed top-0 pt-12 bg-white z-20"
  >
    <section class="py-2 border-b border-gray-100">
      <ul>
        <SideBarNavItem label="Home" icon="home" is-active />
        <SideBarNavItem label="Trending" icon="trending" />
        <SideBarNavItem label="Subscriptions" icon="subscriptions" />
      </ul>
    </section>

    <section class="py-2 border-b border-gray-100">
      <ul>
        <SideBarNavItem label="Library" icon="library" />
        <SideBarNavItem label="History" icon="history" />
      </ul>
    </section>

    <section class="px-8 py-4 border-b font-medium leading-5">
      <span class="text-sm"
        >Sign in to like videos, comment, and subscribe.</span
      >
      <button
        class="flex items-center px-2 py-0.5 mt-3 text-sm text-blue-700 uppercase border border-blue-700 rounded-sm focus:outline-none"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="mr-2 w-7 h-7"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z"
          />
        </svg>
        Sign In
      </button>
    </section>

    <section class="py-2 border-b border-gray-100">
      <div class="uppercase text-sm font-semibold px-6 py-2 text-gray-600">
        Best of youtube
      </div>
      <ul>
        <SideBarCircleNavItem label="Music" icon="music" />
        <SideBarCircleNavItem label="Sports" icon="sports" />
        <SideBarCircleNavItem label="Gaming" icon="gaming" />
        <SideBarCircleNavItem label="Movies" icon="movies" />
        <SideBarCircleNavItem label="News" icon="news" />
        <SideBarCircleNavItem label="Live" icon="live" />
        <SideBarCircleNavItem label="360&deg; Video" icon="video360" />
      </ul>
    </section>

    <section class="py-2 border-b border-gray-100">
      <ul>
        <SideBarNavItem label="Browse channels" icon="browse_channels" />
      </ul>
    </section>

    <section class="py-2 border-b border-gray-100">
      <div class="uppercase text-sm font-semibold px-6 py-2 text-gray-600">
        More from YouTube
      </div>
      <ul>
        <SideBarNavItem label="YouTube Premium" icon="youtube_premium" />
        <SideBarNavItem label="Live" icon="live" />
      </ul>
    </section>

    <section class="py-2 border-b border-gray-100">
      <ul>
        <SideBarNavItem label="Settings" icon="settings" />
        <SideBarNavItem label="Report history" icon="report_history" />
        <SideBarNavItem label="Help" icon="help" />
        <SideBarNavItem label="Send feedback" icon="send_feedback" />
      </ul>
    </section>

    <section class="text-gray-500 px-6 py-4 text-xs font-semibold space-y-4">
      <div>
        <a href="" class="mr-2">About</a>
        <a href="" class="mr-2">Press</a>
        <a href="" class="mr-2">Copyright</a>
        <a href="" class="mr-2">Contact us</a>
        <a href="" class="mr-2">Creators</a>
        <a href="" class="mr-2">Advertise</a>
        <a href="" class="mr-2">Developers</a>
      </div>
      <div>
        <a href="" class="mr-2">Terms</a>
        <a href="" class="mr-2">Privacy</a>
        <a href="" class="mr-2">Policy & Safety</a>
        <a href="" class="mr-2">How YouTube works</a>
        <a href="" class="mr-2">Test new features</a>
      </div>
      <div class="font-normal">&copy; 2021 Google LLC</div>
    </section>
  </aside>
</template>

<script>
import SideBarNavItem from "./SideBarNavItem.vue";
import SideBarCircleNavItem from "./SideBarCircleNavItem.vue";

export default {
  components: {
    SideBarNavItem,
    SideBarCircleNavItem,
  },
};
</script>
