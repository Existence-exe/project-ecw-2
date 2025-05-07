<script setup>
import navbar from "@/components/Navbar.vue";
import hero from "@/components/Hero.vue";
import Homecards from "@/components/Homecards.vue";
import JobListings from "@/components/JobListings.vue";
import { ref } from "vue";
import JobData from '@/jobs2.json' with { type: 'json' };

const data = ref(JobData);
</script>

<template>
  <navbar />
  <hero title="test title" subtitle="hola amijoes" />
  <Homecards />
  <section class="bg-green-50 px-4 py-10">
    <div class="container-xl lg:container m-auto">
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
        Browse Jobs
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobListings
          v-for="job in data"
          :key="job.id"
          :JobDescription="[
            job.type,
            job.title,
            job.description,
            job.salary,
            job.location,
          ]"
        ></JobListings>
      </div>
    </div>
  </section>
</template>
