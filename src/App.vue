<script setup lang="ts">
import Logo from "./icon/logo.svg";
import PlayButton from "./icon/play-button.svg";
import BriefcaseIcon from "./icon/briefcase.svg";
import LocationIcon from "./icon/location.svg";
import ProfileIcon from "./icon/location.svg";
import MenuIcon from "./icon/menu.svg";
import { ref } from "vue";
const menu = ["Home", "About us", "Blogs", "Contact"];
const features = [
  {
    icon: BriefcaseIcon,
    title: "Work-Life Balance",
    description:
      "Many remote jobs also come with flexible schedules, which means that workers can start and end their day as they choose.",
    color: "bg-orange",
  },
  {
    icon: LocationIcon,
    title: "Work Anywhere",
    description:
      "Having access to a broader range of job opportunities that aren’t limited by geographic location. This can be especially helpful.",
    color: "bg-blue",
  },
  {
    icon: ProfileIcon,
    title: "Improved Inclusivity",
    description:
      "Remote work enables companies to embrace diversity and inclusion by hiring people from different backgrounds.",
    color: "bg-pink",
  },
];

const menuAside = ref(false)

const handleMenuAside = () => {
  menuAside.value = !menuAside.value
  console.log(menuAside.value)
}
</script>

<template>
  <div class="w-full min-h-screen font-sans text-gray-900">
    <!-- header -->
    <div class="bg-gradient-to-b from-[#FEE6F7] to-white">

      <img src="/img/blob.svg" alt="" class="absolute top-0 right-0 pointer-events-none">

      <div class="px-6 mx-auto max-w-6xl">
        <div class="flex justify-between items-center py-10">
          <img src="./icon/logo.svg">
          <nav class="hidden md:flex md:items-center md:space-x-10">

            <a v-for="item in menu" href="" class="text-gray-700 hover:text-gray-900">
              {{ item }}
            </a>

            <a href="#" class="font-semibold text-indigo-800">Try now</a>
          </nav>

          <!-- <span class="absolute text-white text-4xl top-5 left-4 cursor-pointer" onclick="Openbar()">
            <i class="bi bi-filter-left px-2 bg-gray-900 rounded-md"></i>
          </span> -->
          <div class="sidebar fixed top-0 right-0 md:right-[-300px] transition-all duration-300 ease-out
    p-2 w-[300px] overflow-y-auto text-center bg-gray-900 shadow h-screen" :class="menuAside ? 'md:left-0' : 'right-[-300px]'">
            <!-- <i class="bi bi-x ml-20 cursor-pointer md:hidden" onclick="handleMenuAside()"></i> -->
            <button class="" @click="handleMenuAside">
            <img :src="MenuIcon" alt="" class="h-10 w-10">
          </button>
          </div>

          <button class="md:hidden" @click="handleMenuAside">
            <img :src="MenuIcon" alt="" class="h-10 w-10">
          </button>
        </div>
      </div>
    </div>
    <!-- body -->
    <div class="px-6 mx-auto max-w-6xl">
      <div class="flex flex-col-reverse items-center md:flex-row lg:items-end">
        <div class="pt-24 w-1/2 pr-8">

          <h1 class="relative z-10 text-5xl font-bold md:text-6xl font-display">
            Learn the
            <span
              class="relative after:content-[url(/img/scratch.svg)] after:absolute after:-top-2 after:-right-6 after:-z-1">
              best
            </span>
            ways for staying
            <span
              class="relative after:content-[url(/img/decoration.svg)] after:absolute after:-bottom-2 after:-right-8 after:-z-1">
              productive
            </span>
          </h1>

          <p class="pt-8 text-lg leading-relaxed text-gray-500 max-w-md md:text-xl">Working at home is definitely a
            convenient
            option and
            makes sense in these unprecedented times</p>

          <div class="flex items-center py-12 space-x-6  md:justify-start">

            <button class="flex justify-center items-center py-4 px-8 font-bold tracking-wide leading-7 text-white bg-blue-600
            rounded-xl">Get Tips</button>

            <button class="flex items-center">
              <img src="./icon/play-button.svg" alt="" class="drop-shadow-lg hover:drop-shadow-xl">
              <span class="pl-4 font-bold tracking-wide">Learn More</span>
            </button>

          </div>
        </div>
        <div class="flex items-end w-1/2 border-b border-gray-400">

          <!-- <img src="/img/illustration.svg" alt=""> -->
          <img src="/img/terms-2.png" alt="">

        </div>
      </div>
    </div>
    <!-- footer -->
    <div class="bg-gray-50">
      <div class="py-12 px-6 mx-auto max-w-6xl">
        <div class="flex gap-x-5">
          <div v-for="feature in features" class="flex flex-col p-8 space-y-4 bg-white border-gray-200">
            <div class="flex items-center space-x-3">
              <div class="relative">
                <span :class="feature.color" class="absolute top-0 left-4 rounded-full w-3 h-3 opacity-60" />
                <img :src="feature.icon" alt="">
              </div>
              <div class="relative">
                <span :class="feature.color" class="absolute right-0 bottom-1 rounded-full w-12 h-1.5 opacity-60" />
                <h2 class="text-xl font-display relative">{{ feature.title }}</h2>
              </div>

            </div>
            <p class="text-sm leading-relaxed text-gray-500">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>