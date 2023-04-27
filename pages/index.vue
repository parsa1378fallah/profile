<template>
  <div>
    <div class="container mx-auto sm:flex border-b-8 border-dotted pt-5 pb-10">
      <div class="sm:w-1/2 lg:w-1/3 flex justify-center mx-auto sm:flex bg-gradient-to-r p-4">
        <div class=" bg-gradient-to-r from-green-500 via-blue-500 to-red-500 w-64 h-64 rounded-full flex justify-center items-center p-4">
          <img src="../assets/images/profile.jpg" class="rounded-full w-full h-full" /> 
        </div>
      </div>
      <div class="sm:w-1/2 lg:w-2/3">
        <div class="w-1/2 mx-auto mt-10 ">
            <p class="text-md text-gray-700">برنامه نویس سمت فرانت</p>
            <h2 class="lg:text-4xl text-3xl text-gray-800 mb-4 flex-nowrap">پارسا فلاح نژاد</h2>
            <p class="text-sm text-gray-600 text-justify">من طراح سایت هستم و عاشق همکاری با تیم ها و شرکت های بزرگ حوزه فناوری و البته چالش های کدنویسی هستم .</p>
        </div>
      </div>
    </div>
    <div class="container mx-auto border-b-8 border-dotted pt-5 pb-10 space-y-6">
      <h3 class="font-bold text-gray-700 text-3xl">مهارت ها</h3>
      <p>فرانت اند</p>
      <div class="flex">
        <div class="w-1/5 border  border-gray-800  py-2 flex flex-col items-center justify-center mt-2 hover:bg-white hover:text-green-500 duration-100 bg-green-500 text-white">
          <VueSvg class="h-6 w-6" color="#fff" />
          <p class="font-semibold">ویو</p>
        </div>
        <div class="w-4/5 flex items-center justify-between border border-gray-900 mt-2 rounded mr-2 px-4 text-gray-900">
          <component
              v-for="(skill, index) in skills"
              :key="index"
              :is="skill.component"
              class="w-8 h-8 md:w-10 md:h-10 p-0.5 "
              :class="skill.color"
              v-tooltip="skill.tooltip"
            ></component>
        </div>
      </div>
    </div> 
    <div  class="container mx-auto sm:flex-col border-b-8 border-dotted pt-5 pb-10">
      <h3 class="font-bold text-gray-700 text-3xl">پروژه ها</h3>
      <div class="mt-16 grid grid-col-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 px-3">
        <div class="border border-black rounded bg-white" 
        v-for="project in projects" :key="project.img">
          <img :src="project.img" class="rounded" />
          <div class="m-6">
            <span class="text-2xl text-gray-900">{{project.title}}</span>
            <div class="mt-4 flex flex-row ">
              <span  class="text-green-100 py-2 px-4 rounded-full mx-1"
              v-for="label in project.labels" :key="label.key" :class="label.color">{{label.key}}</span>
            </div>
          </div>
        </div>
      </div>
    </div>  
  </div>
</template>
<script setup>
import TailwindSvg from "~/components/icons/TailwindSvg.vue";
import BootstrapSvg from "~/components/icons/BootstrapSvg.vue";
import VueSvg from "~/components/icons/vue-svg.vue";
import SassSvg from "~/components/icons/SassSvg.vue";
import NuxtSvg from "~/components/icons/NuxtSvg.vue";
import VuetifySvg from "~/components/icons/VuetifySvg.vue";
import JQuery from "~/components/icons/JQuery.vue";


const skills = [
      {
        component: NuxtSvg,
        color: 'hover:text-green-500',
        tooltip: 'nuxt.js'
      },
      {
        component: VuetifySvg,
        color: 'hover:text-blue-500',
        tooltip: 'vuetify.js'
      },
      {
        component: BootstrapSvg,
        color: 'hover:text-purple-500',
        tooltip: 'bootstrap'
      },
      {
        component: JQuery,
        color: 'hover:text-yellow-500',
        tooltip: 'jQuery'
      },
      {
        component: TailwindSvg,
        color: 'hover:text-green-500',
        tooltip: 'tailwindcss'
      },
      {
        component: SassSvg,
        color: 'hover:text-pink-500',
        tooltip: 'sass'
      }
    ]
const projects = 
[
  {
    img : "/_nuxt/assets/images/1-cart.PNG",
    title : "سبد خرید",
    labels : [
        {
          key  : "vuex",
          color : "bg-green-800"
        },
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
  {
    img : "/_nuxt/assets/images/2-panel.PNG",
    title : "پنل ادمین",
    labels : [
        {
          key  : "vuetify",
          color : "bg-blue-800"
        },
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
  {
    img : "/_nuxt/assets/images/3-music.PNG",
    title : "موزیک پلیر",
    labels : [
        {
          key  : "javascript",
          color : "bg-yellow-800"
        },
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
  {
    img : "/_nuxt/assets/images/4-weather.PNG",
    title : "آب و هوا",
    labels : [
        {
          key  : "rest-api",
          color : "bg-slate-800"
        },
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
  {
    img : "/_nuxt/assets/images/5-calc.PNG",
    title : "ماشین حساب",
    labels : [
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
  {
    img : "/_nuxt/assets/images/6-template.PNG",
    title : "فروشگاه",
    labels : [
        {
          key  : "libraries",
          color : "bg-blue-600"
        },
        {
          key  : "vue.js",
          color : "bg-green-600"
        }
    ]
  },
]
</script>
