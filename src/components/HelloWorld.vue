<template>
  <div class="h-screen">
        <button v-on:click="topMenu" class="fixed right-0 mt-2 text-gray-600 origin-top-right transform bg-white rounded-full shadow-lg opacity-50 text-8xl">
          <i class="fas fa-chevron-circle-up"></i>
        </button>

    <!-- <i @:click="topMenu" class="fixed right-0 mt-2 text-gray-600 origin-top-right transform bg-white rounded-full shadow-lg opacity-50 text-8xl fas fa-chevron-circle-up"></i> -->
    <h1>Conteúdo</h1>
    <div id="a" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-blue-600">ITEM NA DIV #1</div>
    <div id="b" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-green-600">ITEM NA DIV #2</div>
    <div id="c" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-red-600">ITEM NA DIV #3</div>
    <div id="d" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-gray-600">ITEM NA DIV #4</div>
    <div id="e" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-yellow-600">ITEM NA DIV #5</div>
    <div id="f" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-pink-600">ITEM NA DIV #6</div>
    <div id="g" class="h-48 pt-2 pl-2 mb-48 font-semibold text-white bg-black">ITEM NA DIV #7</div>
  </div>
</template>

<script>
export default {
  name: "HelloWord",
  data () {
    return {
      name: 'Content'
      
    }
  },
  
  methods: {
    topMenu(){
      console.log('Teste')
      window.scroll({ top: 0, left: 0, behavior: 'smooth' });
    }
  }
}
</script>