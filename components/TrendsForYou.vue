<template>
  <main class="w-[30rem]">
    <TwitSearch />
    <div class="w-full px-5">
      <div class="bg-useGray h-auto rounded-xl overflow-hidden">
        <h1 class="text-normalWhite text-lg font-bold px-3 py-3">
          Trends for you
        </h1>
        <ul class="flex flex-col px-2 text-normalWhite">
          <li
            v-for="trend in trendsForYou"
            :key="trend.id"
            class="flex px-2 py-1 cursor-pointer hover:bg-lowWhite justify-between items-start"
          >
            <div class="flex flex-col">
              <span class="text-[12px] text-lowsWhite font-light">{{
                trend.trending
              }}</span>
              <span class="text-sm font-bold">{{ trend.title }}</span>
              <span class="text-[12px] text-lowsWhite font-light"
                >{{ trend.twitCount }} tweet</span
              >
            </div>
            <div
              tabindex="10"
              class="cursor-pointer relative group rounded-full p-2 fill-lowsWhite hover:fill-tickBlue hover:bg-hoverBlue z-100 transition duration-200"
            >
              <svg viewBox="0 0 24 24" class="w-[15px]" aria-hidden="true">
                <g>
                  <path
                    d="M3 12c0-1.1.9-2 2-2s2 .9 2 2-.9 2-2 2-2-.9-2-2zm9 2c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm7 0c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2z"
                  ></path>
                </g>
              </svg>
              <div
                class="absolute opacity-0 shadow-[rgba(222,222,222,0.6)] shadow-[0_0_7px_0] overflow-hidden text-normalWhite rounded-xl text-sm w-64 bg-black z-100 pointer-events-none group-focus:opacity-100 group-focus:pointer-events-auto -bottom-10 transition duration-200 right-0"
              >
                <div class="flex flex-col">
                  <span
                    class="py-3 px-2 flex items-center gap-2 hover:bg-lowWhite cursor-pointer"
                  >
                    <svg
                      viewBox="0 0 24 24"
                      class="fill-normalWhite w-[18px]"
                      aria-hidden="true"
                    >
                      <g>
                        <path
                          d="M9.5 7c.828 0 1.5 1.119 1.5 2.5S10.328 12 9.5 12 8 10.881 8 9.5 8.672 7 9.5 7zm5 0c.828 0 1.5 1.119 1.5 2.5s-.672 2.5-1.5 2.5S13 10.881 13 9.5 13.672 7 14.5 7zM12 22.25C6.348 22.25 1.75 17.652 1.75 12S6.348 1.75 12 1.75 22.25 6.348 22.25 12 17.652 22.25 12 22.25zm0-18.5c-4.549 0-8.25 3.701-8.25 8.25s3.701 8.25 8.25 8.25 8.25-3.701 8.25-8.25S16.549 3.75 12 3.75zM8.947 17.322l-1.896-.638C7.101 16.534 8.322 13 12 13s4.898 3.533 4.949 3.684l-1.897.633c-.031-.09-.828-2.316-3.051-2.316s-3.021 2.227-3.053 2.322z"
                        ></path>
                      </g>
                    </svg>
                    Not interested in this
                  </span>
                  <span
                    class="py-3 px-2 flex items-center gap-2 hover:bg-lowWhite cursor-pointer"
                  >
                    <svg
                      viewBox="0 0 24 24"
                      class="fill-normalWhite w-[18px]"
                      aria-hidden="true"
                    >
                      <g>
                        <path
                          d="M9.5 7c.828 0 1.5 1.119 1.5 2.5S10.328 12 9.5 12 8 10.881 8 9.5 8.672 7 9.5 7zm5 0c.828 0 1.5 1.119 1.5 2.5s-.672 2.5-1.5 2.5S13 10.881 13 9.5 13.672 7 14.5 7zM12 22.25C6.348 22.25 1.75 17.652 1.75 12S6.348 1.75 12 1.75 22.25 6.348 22.25 12 17.652 22.25 12 22.25zm0-18.5c-4.549 0-8.25 3.701-8.25 8.25s3.701 8.25 8.25 8.25 8.25-3.701 8.25-8.25S16.549 3.75 12 3.75zM8.947 17.322l-1.896-.638C7.101 16.534 8.322 13 12 13s4.898 3.533 4.949 3.684l-1.897.633c-.031-.09-.828-2.316-3.051-2.316s-3.021 2.227-3.053 2.322z"
                        ></path>
                      </g>
                    </svg>
                    This trend is harmful or spammy
                  </span>
                </div>
              </div>
            </div>
          </li>
          <li
            class="text-sm text-useGreen p-2 py-4 hover:bg-lowWhite cursor-pointer"
          >
            Show More
          </li>
        </ul>
      </div>
    </div>
    <div class="w-full h-auto px-5 mt-2">
      <div class="bg-useGray h-auto rounded-xl overflow-hidden">
        <h3 class="text-normalWhite px-2 py-3 font-bold">Who to follow</h3>
        <ul>
          <li
            v-for="follow in followProfile"
            :key="follow.id"
            class="flex p-3 gap-2 items-center justify-center cursor-pointer hover:bg-lowWhite transition duration-200"
          >
            <div class="overflow-hidden">
              <img
                :src="follow.p_image"
                class="w-10 h-10 object-cover rounded-full hover:brightness-90 transition duration-200"
                alt="profile image"
              />
            </div>
            <div class="flex flex-col flex-grow text-[13px]">
              <span class="font-semibold text-normalWhite">{{
                follow.p_name
              }}</span>
              <span class="font-light text-lowsWhite">{{ follow.p_at }}</span>
            </div>
            <button
              class="bg-normalWhite px-3 py-1 rounded-l-2xl rounded-r-2xl text-[13px] font-semibold hover:brightness-90 transition duration-200"
            >
              Follow
            </button>
          </li>
          <li
            class="text-sm text-useGreen p-2 py-4 hover:bg-lowWhite cursor-pointer"
          >
            Show More
          </li>
        </ul>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from "#imports";

const followProfile = ref([
    {id:1, p_image:'/images/1.jpg', p_name:'Sigara Boregi', p_at:'@sigara_boregi'},
    {id:2, p_image:'/images/2.jpg', p_name:'Yogurtlu Biber', p_at:'@yogurtlu-biber'},
    {id:3, p_image:'/images/3.jpg', p_name:'Barbunya Pilaki', p_at:'@barbunya_pilaki'},
])

const trendsForYou = ref([
  {
    id: 1,
    trending: "Sports Trending",
    title: "YÖNETİM İSTİFA",
    twitCount: "3.558",
  },
  {
    id: 2,
    trending: "Trending in Turkey",
    title: "Nuxt3",
    twitCount: "324.234.234",
  },
  {
    id: 3,
    trending: "Sports Trending",
    title: "Tailwindcss",
    twitCount: "3.558",
  },
  { id: 4, trending: "Trending in Turkey", title: "VUE", twitCount: "3.558" },
  {
    id: 5,
    trending: "Sports Trending",
    title: "Lamine Diack",
    twitCount: "3.558",
  },
]);
</script>
