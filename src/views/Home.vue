<script setup>
import { ref } from "vue";
import MdiGithub from "~icons/mdi/github";
import MdiInstagram from "~icons/mdi/instagram";
import Typing from "@components/Typing.vue";

const step = ref(0);
</script>
<template>
    <div class="w-full overflow-y-auto px-8 pt-16 sm:px-12 sm:pt-20 lg:px-16 lg:pt-24">
        <Typing
            v-if="step >= 0"
            @done="step++"
            text="徐弘益"
            class="mb-2 block text-2xl sm:text-3xl lg:text-4xl"
        />
        <Typing v-if="step >= 1" @done="step++" text="A student who studies at HYSH. And you can call me Andy Hsu." :speed="80" />
        <a
            v-if="step >= 2"
            class="mt-8 flex items-center text-lg text-purple-700 transition-all hover:text-purple-400"
            href="https://app.circleci.com/projects/project-dashboard/github/AndyHsu0506/"
            target="_blank"
        >
            <MdiGithub class="mr-1 inline-block" />
            <Typing v-if="step >= 2" @done="step++" text="GitHub" :speed="80" />
        </a>
        <a
            v-if="step >= 3"
            @done="step++"
            class="mt-4 flex items-center text-lg text-purple-700 transition-all hover:text-purple-400"
            href="https://www.instagram.com/hongyi143/"
            target="_blank"
        >
            <MdiInstagram class="mr-1 inline-block" />
            <Typing v-if="step >= 3" @done="step++" text="Instagram" :speed="80" />
        </a>
    </div>
</template>
