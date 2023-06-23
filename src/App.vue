<template>
    <Navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index: any) => activePage = index"
    ></Navbar>
    
    <PageViewer
    :page="pages[activePage]"
    ></PageViewer>
    
    <Landing/>
    <Booking/>
    
</template>

<script lang="ts">
import PageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';
import Landing from './components/Landing.vue';
import Booking from './components/Booking.vue'

export default {
    components: {
        Navbar,
        PageViewer,
        Landing,
        Booking
    },
    data() {
        return {
            activePage: 0,
            pages: [
                {
                    link: {text: 'Home', url: 'index.html'},
                    pageTitle: 'Home Page',
                    content: 'This is home content'
                },
                {
                    link: {text: 'About', url: 'about.html'},
                    pageTitle: 'About Page',
                    content: 'This is about content'
                },
                {
                    link: {text: 'Contact', url: 'contact.html'},
                    pageTitle: 'Contact Page',
                    content: 'This is contact content'
                },
                {
                    link: {text: 'Vehicle models', url: 'vehicles.html'},
                    pageTitle: 'Vehicles Page',
                    content: 'This is vehicles content'
                },

            ]
        }
    }
}
</script>