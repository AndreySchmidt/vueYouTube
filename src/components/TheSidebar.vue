<template>
  <aside
    class="hidden xl:block w-64 max-h-screen overflow-auto fixed top-0 pt-12 bg-white z-20"
  >
    <SideBarSection>
      <ul>
        <SideBarNavItem label="Home" icon="home" is-active />
        <SideBarNavItem label="Trending" icon="trending" />
        <SideBarNavItem label="Subscriptions" icon="subscriptions" />
      </ul>
    </SideBarSection>

    <SideBarSection>
      <ul>
        <SideBarNavItem label="Library" icon="library" />
        <SideBarNavItem label="History" icon="history" />
      </ul>
    </SideBarSection>

    <SideBarSection class="px-8 py-4 border-b font-medium leading-5">
      <span class="text-sm"
        >Sign in to like videos, comment, and subscribe.</span
      >
      <ButtonSignIn
        class="flex items-center px-2 py-0.5 mt-3 text-sm text-blue-700 uppercase border border-blue-700 rounded-sm focus:outline-none"
      />
    </SideBarSection>

    <SideBarSection>
      <SideBarSectionHeading title="Best of YouTube" />
      <ul>
        <SideBarCircleNavItem label="Music" icon="music" />
        <SideBarCircleNavItem label="Sports" icon="sports" />
        <SideBarCircleNavItem label="Gaming" icon="gaming" />
        <SideBarCircleNavItem label="Movies" icon="movies" />
        <SideBarCircleNavItem label="News" icon="news" />
        <SideBarCircleNavItem label="Live" icon="live" />
        <SideBarCircleNavItem label="360&deg; Video" icon="video360" />
      </ul>
    </SideBarSection>

    <SideBarSection>
      <ul>
        <SideBarNavItem label="Browse channels" icon="browse_channels" />
      </ul>
    </SideBarSection>

    <SideBarSection>
      <SideBarSectionHeading title="More from YouTube" />
      <ul>
        <SideBarNavItem label="YouTube Premium" icon="youtube_premium" />
        <SideBarNavItem label="Live" icon="live" />
      </ul>
    </SideBarSection>

    <SideBarSection>
      <ul>
        <SideBarNavItem label="Settings" icon="settings" />
        <SideBarNavItem label="Report history" icon="report_history" />
        <SideBarNavItem label="Help" icon="help" />
        <SideBarNavItem label="Send feedback" icon="send_feedback" />
      </ul>
    </SideBarSection>

    <SideBarSection
      class="text-gray-500 px-6 py-4 text-xs font-semibold space-y-4"
    >
      <TheFooter />
    </SideBarSection>
  </aside>
</template>

<script>
import SideBarSection from "./SideBarSection.vue";
import SideBarNavItem from "./SideBarNavItem.vue";
import SideBarCircleNavItem from "./SideBarCircleNavItem.vue";
import SideBarSectionHeading from "./SideBarSectionHeading.vue";
import ButtonSignIn from "./ButtonSignIn.vue";
import TheFooter from "./TheFooter.vue";

export default {
  components: {
    SideBarSection,
    SideBarNavItem,
    SideBarCircleNavItem,
    SideBarSectionHeading,
    ButtonSignIn,
    TheFooter,
  },
};
</script>
