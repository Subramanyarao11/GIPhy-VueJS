<template>
  <div class="w-screen h-screen flex flex-col overflow-hidden bg-hero bg-fixed bg-cover justify-center gap-5">
     <h1 class="mt-8 bg-gradient-to-br from-white via-[#f5eaef] to-[#5f4a54] bg-clip-text text-center text-4xl font-medium tracking-tight text-transparent md:text-7xl">
      Search and Share <br />
      GIFs Instantly
    </h1>
    <Search />
  </div>
</template>


<script>
  import Search from './components/Search.vue'
export default{
name: 'App',
components: {
	Search
}}
</script>
