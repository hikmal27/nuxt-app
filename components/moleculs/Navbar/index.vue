<template>
    <div>
        <div class="hidden lg:block px-16 pt-8 pb-2">
            <nav class="w-full flex justify-between items-center">
                <nuxt-link to="">
                    <img src="~/assets/img/logo.svg" alt="Logo SmartIncome">
                </nuxt-link>
                <div class="flex text-teal-700">
                    <TopMenu v-for="menus in linksList" :key="menus" v-bind="menus" />
                </div>
                <div class="flex bg-gray-200 text-teal-700 px-1 py-1 rounded-full shadow-lg">

                    <router-link to="/business" :class="MenuNyala ? 'bg-yellow-300 rounded-full font-semibold' : 'bg-yellow-300 rounded-full font-semibold'" @click="linksActive()">
                        <div class="px-3 py-2">
                            <p>Business</p>
                        </div>
                    </router-link>
                    <router-link to="/personal">
                        <div class="px-3 py-2">
                            <p>Personal</p>
                        </div>
                    </router-link>
                    <!-- <router-link v-for="link in links" :key="link" :to="link.Url" :active="Menu === link.Title" @click="setActive(link.Title)" active-class="bg-yellow-300 rounded-full font-semibold">
                        <div class="px-3 py-2">
                            <p>{{link.Title}}</p>
                        </div>
                    </router-link> -->

                </div>
            </nav>
        </div>
        <div class="hidden lg:block px-16">
            <nav class="flex justify-end">
                <router-link to="#" class="text-lg no-underline mt-2 text-teal-700 hover:text-teal-800 font-bold ">
                    ID <span class="text-yellow-400">|</span> EN
                </router-link>
            </nav>
        </div>
        <!-- Navbar mobile -->
        <div class="flex justify-between px-3 py-3 lg:hidden">
            <div>
                <router-link to="#">
                  <img src="img/logo.svg" alt="Logo SmartIncome" class="w-3/4">
                </router-link>
            </div>

            <!-- Hamburger menu -->
            <div class="flex items-center">
                <q-icon :name="burgerMenu ? 'eva-close-outline' : 'eva-menu-2-outline'" class="text-3xl text-teal-700" @click="burgerMenu = !burgerMenu"></q-icon>

            </div>
        </div>

        <!-- Dropdown Menu -->
        <nav v-if="burgerMenu === true" class="bg-gray-100 text-teal-700 px-5 transition delay-150 duration-300 ease-in ">
            <div v-for="link in linksList" :key="link.Url" class="px-2 py-2 rounded-md dark-mode:bg-gray-800 hover:bg-teal-700 hover:text-white space-y-2">
                <router-link :to="link.Url">{{ link.MenuTitle }}</router-link>
            </div>
        </nav>
    </div>
</template>

<script>
const linksList = [
    {
        MenuTitle: "Tentang Kami",
        Url: "/business/tentang-kami"
    },
    {
        MenuTitle: "Penawaran",
        Url: "/business/penawaran"
    },
    {
        MenuTitle: "Promo & Event",
        Url: "/business/promo&event"
    },
    {
        MenuTitle: "Blog",
        Url: "/business/blog"
    },
]

export default {
    data() {
        return {
            linksList,

            MenuNyala: false,
            burgerMenu: false,
        }
    }
}
</script>
