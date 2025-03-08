<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="font-primary flex justify-between items-center py-4 px-8 shadow-sm">
    <div class="flex items-center space-x-4">
      <a href="index.html"><img class="w-[144px] h-[32px]" src="../assets/icon/Logo.svg" alt="Logo embrace" /></a>
    </div>

    <!-- Menú para escritorio -->
    <ul class="hidden md:flex gap-[40px] items-center">
      <li><a href="#how-it-works" class="hover:text-primary">How it works</a></li>
      <li><a href="#our-work" class="hover:text-primary">Our work</a></li>
      <li><a href="#pricing" class="hover:text-primary">Pricing</a></li>
      <li><a href="#about-us" class="hover:text-primary">About us</a></li>
    </ul>

    <!-- Botón "Book a call" solo en escritorio -->
    <button class="hidden md:block bg-primary text-white py-2 px-4 rounded-[70px] hover:bg-primary-dark transition duration-300 cursor-pointer">
      Book a call
    </button>

    <!-- Botón de menú hamburguesa -->
    <button @click="toggleMenu" class="md:hidden text-3xl z-50">
      {{ isMenuOpen ? '✕' : '☰' }}
    </button>

     <!-- Menú desplegable con animación -->
    <div
      :class="[
  'fixed inset-0 bg-white flex flex-col items-center justify-center space-y-6 z-40 transform transition-all duration-500 ease-in-out',
  isMenuOpen ? 'translate-x-0 opacity-100' : 'translate-x-full opacity-0'
]"
    >
      <a href="#how-it-works" @click="toggleMenu" class="text-2xl hover:text-primary">How it works</a>
      <a href="#our-work" @click="toggleMenu" class="text-2xl hover:text-primary">Our work</a>
      <a href="#pricing" @click="toggleMenu" class="text-2xl hover:text-primary">Pricing</a>
      <a href="#about-us" @click="toggleMenu" class="text-2xl hover:text-primary">About us</a>
    </div>
  </nav>
</template>





