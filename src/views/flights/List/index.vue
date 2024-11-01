<template>
  <NavBar4 />

  <main>
    <Booking />

    <NoticeBoard />

    <FlightList />
  </main>

  <Footer />

  <BackToTop />
</template>

<script setup lang="ts">
import NavBar4 from '@/views/flights/List/components/NavBar4.vue'
import Booking from './components/Booking.vue'
import NoticeBoard from './components/NoticeBoard.vue'
import FlightList from './components/FlightList.vue'
import Footer from '@/views/flights/List/components/Footer.vue'
import BackToTop from '@/components/BackToTop.vue'
</script>
