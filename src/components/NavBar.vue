<template>
    <div id="navbar" class="flex flex-row flex-wrap justify-between w-full h-20 font-sans text-white bg-gray-800 md:gap-3">
        <div class="flex flex-row flex-wrap self-center text-2xl border-r-2 border-gray-600">
            <div class="px-2 py-2 ">
                <img class="w-16 h-16" src="../assets/logo.png" alt="Avatar">
            </div>
            <div class="self-center hidden pr-2 cursor-default sm:block">
                <a href="#" class="menu">Sistema</a>
            </div>
        </div>

        
        <div class="flex-row self-center flex-grow hidden gap-6 font-medium md:flex">
            <div class="menu"><a href="#a">Item 1</a></div>
            <div class="menu"><a href="#b">Item 2</a></div>
            <div class="menu"><a href="#c">Item 3</a></div>
            <div class="menu"><a href="#d">Item 4</a></div>
            <div class="menu"><a href="#e">Item 5</a></div>
        </div>

        <div v-on:click="viewMenu" class="flex-row self-center flex-grow ml-2 md:hidden">
            <i class="text-3xl fas fa-bars"></i>
            <div :class="menu.value" class="absolute w-56 mt-2 font-sans font-medium text-black origin-top-right bg-white rounded-md shadow-lg sm:left-56 left-32 ring-1 ring-black ring-opacity-5 focus:outline-none" role="menu" aria-orientation="vertical" aria-labelledby="menu-button" tabindex="-1">
                <div class="mt-2 ml-1 border-b-2"><a href="#a">Item 1</a></div>
                <div class="mt-2 ml-1 border-b-2"><a href="#b">Item 2</a></div>
                <div class="mt-2 ml-1 border-b-2"><a href="#c">Item 3</a></div>
                <div class="mt-2 ml-1 border-b-2"><a href="#d">Item 4</a></div>
                <div class="mt-2 ml-1"><a href="#">Item 5</a></div>
            </div>
        </div>

        <div v-on:click.stop.prevent="alternate" class="flex justify-end bg-gray-800 border-gray-600 md:border-l-2 md:w-725 profile" v-if="profile.visible == true">
            <div class="px-2 py-2 ">
                <img class="w-16 h-full duration-500 ease-in-out transform border-4 rounded-full border-opacity-60 hover:text-green-300 hover:scale-125" src="../assets/1611055565226.jpg" alt="Avatar">
            </div>
            <div class="self-center justify-end hidden pr-2 font-medium text-white cursor-pointer md:block hover:text-green-300 hover:scale-125">
                <span>Paulo Roberto Torres</span>
            </div>
        </div>
    </div>

    <div id="outer-container" class="absolute right-0 float-right transition duration-150 ease-in-out origin-top-right bg-gray-800 rounded-md rounded-b-sm shadow-lg top-2 ring-1 ring-black ring-opacity-5 focus:outline-none w-80 profile-menu" v-if="profileMenu.visible == true" >
        <div class="absolute right-0 float-right text-3xl text-right text-white transition duration-150 ease-in-out origin-top-right bg-gray-800 rounded-md rounded-b-sm shadow-lg hover:text-green-500 top-2 ring-1 ring-black ring-opacity-5 focus:outline-none w-80 profile-menu" v-if="profileMenu.visible == true" >
           
            <a href="#" v-on:click.stop.prevent="alternate">
                <i class="mx-2 fas fa-chevron-circle-up"></i>
            </a>
        </div>

        <div class="flex justify-center pt-3 pb-2">
            <img class="w-48 h-full duration-500 ease-in-out transform border-4 rounded-full hover:border-green-200 border-opacity-60" src="../assets/1611055565226.jpg" alt="Avatar">
        </div>
        <div class="text-xl font-medium text-white">
            <p class="text-center">Paulo Roberto Torres</p>
        </div>
        <div class="flex flex-row justify-between pt-5 mt-5 font-medium text-white border-t-2 border-opacity-50">
            <div class="px-3 pt-2 m-2 border rounded-md cursor-pointer hover:border-green-800 hover:bg-green-500">
                <a href="#">Perfil</a>
            </div>
             <div class="px-3 py-1 m-2 cursor-pointer hover:text-green-500">
                <a href="#" v-on:click.stop.prevent="alternate">
                    <i class="text-3xl fas fa-angle-up"></i>
                </a>
            </div>
            <div class="px-3 pt-2 m-2 border rounded-md cursor-pointer hover:border-green-800 hover:bg-green-500">
                    <a href="#">Sair</a>
            </div>
        </div>
    </div>

</template>

<script>
export default {
    props: ['image'],

    data () {
        return {
            profileMenu: {
                visible: false
            },
            profile: {
                visible: true
            },
            menu: {
                value:'hidden'
            },

            name: 'Navbar'
        }
    },
    
    methods: {
        alternate () {
            this.profileMenu.visible = !this.profileMenu.visible
            this.profile.visible = !this.profile.visible
            return 0
        },

        viewMenu () {
            if(this.menu.value == 'hidden') {
                this.menu.value = ''
            } else {
                this.menu.value = 'hidden'
            }
        }
    }
}
</script>