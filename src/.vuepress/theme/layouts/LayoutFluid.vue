<template>
    <v-app>
        <ClientOnly>
            <top-nav />
        </ClientOnly>
        <v-main>
            <v-fade-transition appear hide-on-leave>
                <Content :key="new Date().toString()" />
            </v-fade-transition>
        </v-main>
        <app-footer />
    </v-app>
</template>

<script>
import AppFooter from '../components/AppFooter.vue'
import TopNav from '../components/TopNav.vue'

export default {
    components: { AppFooter, TopNav },
}
</script>

<style>
.fade-enter-active,
.fade-leave-active {
    transition-property: opacity;
    transition-duration: 0.5s;
}

.fade-enter-active {
    transition-delay: 0.5s;
}

.fade-enter,
.fade-leave-active {
    opacity: 0;
}

.typing-h2 {
    min-height: 2.2rem;
}
</style>