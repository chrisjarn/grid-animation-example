<template>
  <div
    class="max-w-7xl md:pb-0 pb-10 mx-auto flex items-center md:h-svh px-5 md:px-0 justify-center"
  >
    <div class="grid grid-cols-1 md:grid-cols-4 sm:grid-cols-1 gap-3 mt-6 px-0">
      <!-- Join & Play -->
      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] overflow-hidden group relative cursor-pointer h-[300px] p-6 rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] transition-all duration-200 md:col-span-2"
      >
        <MainLogo
          class="md:w-80 md:h-80 w-100 h-100 text-white/[2%] -rotate-5 absolute md:top-8 top-0 left-10"
        />
        <div class="flex flex-col items-start space-y-1 relative z-[99999]">
          <div class="flex items-center gap-2">
            <HandMetal class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              Join the Elite
            </h2>
          </div>
          <p class="text-muted-foreground text-sm max-w-xs relative z-[99999]">
            Get exclusive access to our
            <span class="text-white">gaming platform</span> and
            <span class="text-white">giveaway system</span> with a premium
            membership. Play, compete, and win like never before.
          </p>
        </div>
        <div class="mt-10 space-y-2 relative z-[99999]">
          <div class="flex items-center gap-2">
            <Check
              class="w-4.5 h-4.5 text-white group-hover:text-purple-500 transition-colors duration-200"
            />
            <span
              class="text-white text-xs font-medium font-mono group-hover:text-purple-500 transition-colors duration-200"
            >
              Play, Compete, and Win
            </span>
          </div>
          <div class="flex items-center gap-2">
            <Check
              class="w-4.5 h-4.5 text-white group-hover:text-purple-500 transition-colors duration-200"
            />
            <span
              class="text-white text-xs font-medium font-mono group-hover:text-purple-500 transition-colors duration-200"
            >
              Win Prizes & Credits
            </span>
          </div>
          <div class="flex items-center gap-2">
            <Check
              class="w-4.5 h-4.5 text-white group-hover:text-purple-500 transition-colors duration-200"
            />
            <span
              class="text-white text-xs font-medium font-mono group-hover:text-purple-500 transition-colors duration-200"
            >
              Impactful Gaming
            </span>
          </div>
          <div class="flex items-center gap-2">
            <Check
              class="w-4.5 h-4.5 text-white group-hover:text-purple-500 transition-colors duration-200"
            />
            <span
              class="text-white text-xs font-medium font-mono group-hover:text-purple-500 transition-colors duration-200"
            >
              Powerful Community
            </span>
          </div>
        </div>
      </div>

      <!-- Earn Credits -->
      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] group cursor-pointer p-6 rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] transition-all duration-200"
        @mouseenter="
          isHovered = true;
          generateRandomNumber();
        "
        @mouseleave="isHovered = false"
      >
        <div class="flex flex-col items-start space-y-1">
          <div class="flex items-center gap-2">
            <Coins class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              EARN & STACK
            </h2>
          </div>
          <p class="text-muted-foreground text-sm leading-relaxed">
            <span class="text-white"> Win games to earn credits</span>, plus get
            monthly credit bonuses with your membership. Your credits never
            expire, so keep stacking them up
          </p>
        </div>
        <div class="mt-7">
          <div class="flex items-center gap-1">
            <Coins
              fill="currentColor"
              class="w-10 h-10 translate-y-2 text-[#333638] group-hover:text-yellow-500 transition-colors duration-200"
            />
            <NumberFlow
              :value="isHovered ? randomValue : 100"
              class="text-[#333638] group-hover:text-yellow-500 italic text-6xl font-black"
            />
          </div>
        </div>
      </div>

      <!-- Win Prizes -->
      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] relative overflow-hidden p-6 rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] transition-all duration-200 group cursor-pointer"
      >
        <div class="flex flex-col items-start space-y-1">
          <div class="flex items-center gap-2">
            <Award class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              Win Big
            </h2>
          </div>
          <p class="text-muted-foreground text-sm leading-relaxed">
            <span class="text-white"
              >Use your credits in exclusive raffles to win amazing
              prizes.</span
            >
            From gaming gear to tech gadgets.
          </p>
          <div class="w-full mt-10">
            <div class="flex w-full items-center gap-2">
              <div
                class="w-full h-20 flex items-center justify-center rounded-lg border border-[#333638] bg-[#161819] relative overflow-hidden"
              >
                <div
                  class="flex flex-col gap-6 items-center absolute top-6 transition-all duration-[1000ms] ease-in-out group-hover:-translate-y-[335px]"
                >
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Gem class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <MainLogo class="w-6 h-6 text-green-500" />
                </div>
              </div>
              <div
                class="w-full h-20 flex items-center justify-center rounded-lg border border-[#333638] bg-[#161819] relative overflow-hidden"
              >
                <div
                  class="flex flex-col gap-6 items-center absolute top-6 -translate-y-6 transition-all duration-[1000ms] ease-in-out delay-[200ms] group-hover:-translate-y-[335px]"
                >
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <Gem class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <MainLogo class="w-6 h-6 text-green-500" />
                </div>
              </div>
              <div
                class="w-full h-20 flex items-center justify-center rounded-lg border border-[#333638] bg-[#161819] relative overflow-hidden"
              >
                <div
                  class="flex flex-col gap-6 items-center absolute top-6 transition-all -translate-y-11 duration-[1000ms] ease-in-out delay-[400ms] group-hover:-translate-y-[335px]"
                >
                  <Gem class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <Gem class="w-8 h-8 text-[#323538]" />
                  <Crown class="w-8 h-8 text-[#323538]" />
                  <Trophy class="w-8 h-8 text-[#323538]" />
                  <MainLogo class="w-6 h-6 text-green-500" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] cursor-pointer overflow-hidden h-[300px] group p-6 rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] transition-all duration-200"
        @mouseenter="isMultiplayerHovered = true"
        @mouseleave="isMultiplayerHovered = false"
      >
        <div class="flex relative flex-col items-start space-y-1">
          <div class="flex items-center gap-2">
            <Swords class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              Play Multiplayer
            </h2>
          </div>
          <p class="text-muted-foreground text-sm leading-relaxed z-[999999]">
            <span class="text-white">Challenge other players</span> in
            competitive matches and climb the ranks to prove your skills.
          </p>

          <div class="absolute opacity-80 top-14 left-1/2 -translate-x-1/2">
            <motion.div
              :initial="{ width: 0 }"
              :animate="
                isMultiplayerHovered ? { width: '200px' } : { width: 0 }
              "
              :transition="{ type: 'spring', stiffness: 300, damping: 25 }"
              class="border-t border-b border-blue-400 bg-blue-900/50 absolute right-30 top-20 h-10 z-[9] flex items-center justify-end overflow-hidden"
            >
              <span class="italic font-bold text-blue-400 text-xl pr-8"
                >FIGHT</span
              >
            </motion.div>
            <motion.div
              :initial="{ width: 0 }"
              :animate="
                isMultiplayerHovered ? { width: '200px' } : { width: 0 }
              "
              :transition="{ type: 'spring', stiffness: 300, damping: 25 }"
              class="border-t border-b border-red-400 bg-red-900/50 absolute left-28 top-39 h-10 z-[9] flex items-center justify-start overflow-hidden"
            >
              <span class="italic font-bold text-red-400 text-xl pl-7"
                >FIGHT</span
              >
            </motion.div>
            <svg
              class="z-[9999999] group-hover:scale-110 transition duration-200 relative"
              width="156"
              height="240"
              viewBox="0 0 156 284"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M0.295618 283.329C0.562576 282.834 2.85438 278.436 5.38851 273.555C16.8901 251.406 34.7612 217.747 48.3767 192.59C50.9143 187.901 52.3473 185.01 52.1691 184.938C52.0116 184.875 46.1319 184.794 39.1031 184.759L26.3234 184.695L24.8505 178.007C20.8848 160.003 16.2587 139.051 15.5375 135.827C15.0944 133.847 13.3163 125.803 11.5862 117.952C6.6099 95.3712 6.22988 93.6481 4.11267 84.0651L2.10926 74.9972L18.017 75.0633L33.9247 75.1294L36.8591 90.4325C39.7146 105.324 40.8135 111.969 44.3446 135.699C45.2813 141.994 46.1264 147.357 46.2227 147.616C46.352 147.965 48.9679 142.789 56.2318 127.812C61.6406 116.66 68.6711 102.501 71.8554 96.348C75.0396 90.1946 78.8235 82.8742 80.2641 80.0804L82.8833 75.0008L97.983 74.9977L113.083 74.9946L114.978 71.5898C126.11 51.5913 155.11 0.79177 155.83 0.0281835C155.964 -0.113274 155.801 0.291809 155.468 0.928367C155.135 1.56493 153.273 5.1528 151.331 8.90142C136.165 38.1711 113.547 80.5447 92.5719 118.981C89.6771 124.286 85.3218 132.272 82.8934 136.727C80.465 141.183 76.3025 148.764 73.6433 153.574C70.9842 158.383 67.2132 165.212 65.2634 168.748C53.8628 189.425 37.1452 219.299 25.0379 240.63C13.8415 260.356 0.482085 283.538 0.0602696 283.972C-0.0772485 284.113 0.02866 283.824 0.295618 283.329Z"
                class="transition-colors duration-300 fill-[#383B3E] group-hover:fill-blue-400"
              />

              <path
                class="translate-y-32 translate-x-11 transition-colors duration-300 fill-[#383B3E] group-hover:fill-red-400"
                d="M36.1561 114.676C23.0454 113.741 13.722 110.039 5.95566 102.683C4.28802 101.104 0.52984 96.8146 0.115173 96.0174C-0.139672 95.5275 -0.224082 95.6248 5.91478 89.3329C7.16387 88.0527 10.4828 84.6349 13.2901 81.7379C16.0974 78.8408 18.4939 76.4309 18.6157 76.3825C18.7374 76.334 19.8426 77.3286 21.0716 78.5927C27.2268 84.9234 34.5193 87.9561 44.5233 88.3454C50.5009 88.5779 54.9248 87.8012 58.6392 85.867C62.1609 84.0331 63.9781 81.5755 64.1929 78.3561C64.3343 76.2373 63.7608 74.7742 62.2152 73.3106C59.5343 70.7717 55.5691 69.5282 46.883 68.5023C33.3085 66.899 24.9854 63.7334 19.4377 58.0639L17.6243 56.2107L18.1824 55.1526C18.4893 54.5707 22.9879 46.398 28.1792 36.9911C33.3705 27.5841 39.8994 15.7107 42.6879 10.6055L47.7579 1.32345L51.1609 0.832104C55.9192 0.145057 67.5631 0.134663 71.7764 0.813573C81.948 2.45291 89.4885 5.96917 96.2745 12.2375L97.1054 13.0051L95.2654 15.1094C94.2534 16.2667 90.3398 20.6076 86.5685 24.7557L79.7116 32.2978L78.653 31.4284C74.7003 28.1824 68.9112 25.9898 63.1701 25.5644C62.1183 25.4864 60.3919 25.361 59.3338 25.2857C58.2758 25.2104 56.178 25.2651 54.6721 25.4071C46.868 26.1438 42.2484 29.289 41.8392 34.1446C41.5635 37.4161 43.0785 39.6835 46.3865 40.9501C48.49 41.7555 50.864 42.2153 56.4609 42.9015C71.5967 44.7571 82.1788 49.8643 88.1345 58.1879C91.8049 63.3175 93.4503 70.0206 92.9189 77.6794C92.3082 86.483 89.573 93.3927 84.3708 99.274C77.0228 107.581 66.4435 112.456 51.8193 114.273C48.0827 114.737 39.952 114.947 36.1561 114.676Z"
              />
            </svg>
          </div>
        </div>
      </div>
      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] cursor-pointer relative h-[300px] overflow-hidden md:col-span-2 p-6 rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] group transition-all duration-200"
      >
        <div class="flex flex-col items-start space-y-1">
          <div
            class="absolute group-hover:bg-gradient-to-r group-hover:from-transparent group-hover:via-indigo-500 group-hover:to-transparent left-10 top-1/2 rotate-125 bg-gradient-to-r from-transparent via-[#4A4D50] to-transparent h-[2px] w-full blur-sm"
          />
          <div
            class="absolute left-10 opacity-80 top-1/2 group-hover:bg-gradient-to-r group-hover:from-transparent group-hover:via-indigo-500 group-hover:to-transparent rotate-125 bg-gradient-to-r from-transparent via-[#4A4D50] to-transparent h-px w-full"
          />

          <div class="flex items-center gap-2">
            <Handshake class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              Play With friends
            </h2>
          </div>
          <p class="text-muted-foreground text-sm leading-relaxed max-w-xs">
            <span class="text-white">Team up with friends</span> and dominate
            together. Invite your squad, join forces, and experience gaming at
            its best.
          </p>
          <div class="mt-6 flex opacity-90 items-center mx-auto gap-34">
            <div
              class="rounded-full text-white py-2.5 group-hover:bg-indigo-500 relative px-4 bg-[#2A2D30] transition-transform duration-300 group-hover:-translate-x-11 group-hover:translate-y-16"
            >
              <p
                class="text-muted-foreground text-xs group-hover:text-white font-medium"
              >
                @christiaanuttam
              </p>
              <MousePointer2
                fill="#2A2D30"
                class="w-8 h-8 text-[#2A2D30] absolute -top-4 -right-7 rotate-100 group-hover:fill-indigo-500 group-hover:text-indigo-500"
              />
            </div>
            <div
              class="rounded-full text-white py-2.5 translate-y-16 group-hover:bg-sky-500 relative px-4 bg-[#2A2D30] transition-transform duration-300 group-hover:translate-x-11 group-hover:translate-y-0"
            >
              <p
                class="text-muted-foreground group-hover:text-white text-xs font-medium"
              >
                @domkali
              </p>
              <MousePointer2
                fill="#2A2D30"
                class="w-8 h-8 text-[#2A2D30] absolute -top-4 -left-7 -rotate-10 group-hover:fill-sky-500 group-hover:text-sky-500"
              />
            </div>
          </div>
        </div>
      </div>

      <div
        class="bg-[linear-gradient(to_top,#1A1C1E,#242729)] cursor-pointer overflow-hidden h-[300px] relative rounded-xl shadow-[0_1px_2px_rgba(0,0,0,0.3),0_2px_6px_rgba(0,0,0,0.2)] hover:shadow-[0_2px_4px_rgba(0,0,0,0.3),0_3px_8px_rgba(0,0,0,0.2)] transition-all duration-200 group"
      >
        <div class="flex flex-col items-start space-y-1 pt-6 px-6">
          <div class="flex items-center gap-2">
            <Crown class="w-5.5 h-5.5 text-white" />
            <h2 class="text-lg font-bold uppercase tracking-tight text-white">
              LEADERBOARDS
            </h2>
          </div>
          <p class="text-muted-foreground text-sm leading-relaxed">
            Compete daily. <span class="text-white">Rise to the top.</span>
          </p>
        </div>
        <div class="mt-10 space-y-2 relative">
          <div
            class="h-auto bg-[#2A2E2F] z-[99999] items-center gap-2 relative w-[65%] ml-auto p-0.5 flex rounded-l-full"
          >
            <div class="w-9 h-9 bg-[#202224] rounded-full overflow-hidden">
              <div
                class="flex items-center opacity-80 justify-center translate-y-1 -translate-x-0"
              >
                <Avatar1 />
              </div>
            </div>
            <h1
              class="font-medium text-muted-foreground text-xs z-[9999] group-hover:text-white transition duration-200"
            >
              @DomKali
            </h1>
            <h1
              class="text-end font-bold text-2xl absolute right-1.5 font-mono uppercase text-[#161819]/80"
            >
              2<span class="text-base">nd</span>
            </h1>
          </div>
          <div
            class="h-auto p-0.5 flex items-center gap-2 w-[90%] bg-[#333638] ml-auto rounded-l-full relative"
          >
            <div
              class="w-9 h-9 bg-[#202224] group-hover:bg-teal-500 transition duration-200 rounded-full"
            >
              <div
                class="flex items-center justify-center translate-y-0.5 -translate-x-0"
              >
                <div
                  class="absolute inset-0 flex -z-10 items-center -top-0 justify-center"
                >
                  <div
                    class="w-[200px] h-[200px] rounded-full border border-[#333638]/20 absolute"
                  ></div>
                  <div
                    class="w-[160px] h-[160px] rounded-full border border-[#333638]/30 absolute"
                  ></div>
                  <div
                    class="w-[120px] h-[120px] rounded-full border border-[#333638]/40 absolute"
                  ></div>
                  <div
                    class="w-[80px] h-[80px] rounded-full border border-[#333638]/50 absolute"
                  ></div>
                  <div
                    class="w-[40px] h-[40px] rounded-full group-hover:bg-[#333638]/60 group-hover:animate-ping absolute"
                  ></div>
                </div>
                <div
                  class="translate-y-[2.5px] group-hover:opacity-90 relative"
                >
                  <Avatar2 />
                </div>
              </div>
            </div>
            <h1
              class="font-medium text-muted-foreground text-xs z-[9999] group-hover:text-teal-500 transition-all duration-200"
            >
              @ChrisJarn
            </h1>
            <h1
              class="text-end font-bold text-2xl absolute right-1.5 group-hover:text-teal-500 transition duration-200 font-mono uppercase text-[#161819]/80"
            >
              1<span class="text-base">st</span>
            </h1>
          </div>
          <div
            class="h-auto p-0.5 w-[70%] flex items-center gap-2 z-[99999] relative bg-[#272A2C] ml-auto rounded-l-full"
          >
            <div class="w-9 h-9 bg-[#202224] rounded-full overflow-hidden">
              <div
                class="flex items-center justify-center translate-y-1.5 -translate-x-0"
              >
                <Avatar3 />
              </div>
            </div>
            <h1
              class="font-medium text-muted-foreground text-xs group-hover:text-white transition duration-200"
            >
              @FearSaniyha
            </h1>
            <h1
              class="text-end font-bold text-2xl absolute right-1.5 font-mono uppercase text-[#161819]/80"
            >
              3<span class="text-base">rd</span>
            </h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import {
  HandMetal,
  Coins,
  Award,
  Swords,
  Handshake,
  MousePointer2,
  Crown,
  Trophy,
  Gem,
  Check,
} from "lucide-vue-next";
import NumberFlow from "@number-flow/vue";
import { motion } from "motion-v";
import MainLogo from "./assets/MainLogo.vue";
import Avatar3 from "./assets/Avatar3.vue";
import Avatar2 from "./assets/Avatar2.vue";
import Avatar1 from "./assets/Avatar1.vue";
const isHovered = ref(false);
const randomValue = ref(100);
const isMultiplayerHovered = ref(false);

// Function to generate random number on each hover
const generateRandomNumber = () => {
  randomValue.value = Math.floor(Math.random() * (2000 - 1000 + 1)) + 1000;
};
</script>
