<script setup>
import About from './About.vue';
import Portfolio from './Portfolio.vue';
</script>

<template>
    <div class="page-wrapper">
        <div class="top-bar">
            <div class="main-nav">
                <v-tabs fixed-tabs>
                    <v-tab class="nav-tab" @click="page = 0" prepend-icon="mdi-account-outline">
                        About Me
                    </v-tab>
                    <v-tab class="nav-tab" @click="page = 1" prepend-icon="mdi-pencil-outline">
                        Projects
                    </v-tab>
                </v-tabs>
            </div>
        </div>
        <div class="content">
            
            <Transition mode="out-in">
                <About v-if="page == 0" />
                <Portfolio v-else-if="page == 1" />
            </Transition>
        </div>


    </div>
</template>

<script>
export default {
    name: 'Page',
    data() {
        return {
            page: 0,
        }
    },
    methods: {
    }
}
</script>

<style lang="scss">
.page-wrapper {
    height: 100vh;
    width: 100vw;
}

.nav-tab {
    width: 50%
}

.v-enter-active,
.v-leave-active {
    transition: opacity 0.25s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}

.top-bar {
    position: fixed;
    width: 100%;
    height: 50px;
}

.content {
    top: 50px;
    position: relative;
}
</style>