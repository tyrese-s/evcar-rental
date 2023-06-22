<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <div class='container-fluid'>
            <a class="navbar-brand" href="'#'">EV-car rental</a>
            <i class="bi bi-ev-front"></i>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <navbar-link
                        :page="page"
                        :isActive="activePage === index"
                        @click.prevent="navLinkClick(index)"

                    ></navbar-link>
                    <!-- <a class="nav-link"
                    :class="{active: activePage == index}"
                    aria-current="page"
                    :href="page.link.url"
                    :title="`This link goes to the ${page.link.text} page`"
                    @click.prevent="navLinkClick(index)"
                    >{{ page.link.text }}</a> -->
                </li>
            </ul>
            <form class="d-flex">
                <button class="btn btn-primary"
                @click.prevent="changeTheme()"
                >Toggle</button>
            </form>
        </div>
    </nav>

</template>

<script lang="ts">
import NavbarLink from './NavbarLink.vue'
export default {
    components: {
        NavbarLink
    },
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'light',
        }
    },
    methods: {
        changeTheme() {
            let theme = 'light';

            if(this.theme = 'light') {
                theme = 'dark'
            }

            this.theme = theme
        }
    }
}
</script>