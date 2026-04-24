<script setup>
import { useLayout } from '@/layout/composables/layout';
import AppConfigurator from './AppConfigurator.vue';

const { toggleMenu, toggleDarkMode, isDarkTheme } = useLayout();
</script>

<template>
    <div class="layout-topbar">
        <div class="layout-topbar-logo-container">
            <button class="layout-menu-button layout-topbar-action" @click="toggleMenu">
                <i class="pi pi-bars"></i>
            </button>
            <router-link to="/" class="layout-topbar-logo">
                <!-- Espiral do Clã Uzumaki -->
                <svg viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" width="40" height="40">
                    <path
                        d="M20 20
                           m0,-14
                           a14,14 0 1,1 -0.01,0
                           M20 20
                           m0,-10
                           a10,10 0 1,1 -0.01,0
                           M20 20
                           m0,-6
                           a6,6 0 1,1 -0.01,0
                           M20 20
                           m0,-2.5
                           a2.5,2.5 0 1,1 -0.01,0"
                        stroke="var(--primary-color)"
                        stroke-width="2"
                        fill="none"
                    />
                    <path
                        d="M20 6 Q34 6 34 20 Q34 34 20 34 Q6 34 6 20 Q6 10 14 7"
                        stroke="var(--primary-color)"
                        stroke-width="2.5"
                        fill="none"
                        stroke-linecap="round"
                    />
                    <path
                        d="M20 10 Q30 10 30 20 Q30 30 20 30 Q10 30 10 20 Q10 13 16 10.5"
                        stroke="var(--primary-color)"
                        stroke-width="2"
                        fill="none"
                        stroke-linecap="round"
                    />
                    <path
                        d="M20 14 Q26 14 26 20 Q26 26 20 26 Q14 26 14 20 Q14 16 18 14.5"
                        stroke="var(--primary-color)"
                        stroke-width="1.8"
                        fill="none"
                        stroke-linecap="round"
                    />
                    <circle cx="20" cy="20" r="2" fill="var(--primary-color)" />
                </svg>

                <span>UZUMAKI</span>
            </router-link>
        </div>

        <div class="layout-topbar-actions">
            <div class="layout-config-menu">
                <button type="button" class="layout-topbar-action" @click="toggleDarkMode">
                    <i :class="['pi', { 'pi-moon': isDarkTheme, 'pi-sun': !isDarkTheme }]"></i>
                </button>
                <div class="relative">
                    <button
                        v-styleclass="{ selector: '@next', enterFromClass: 'hidden', enterActiveClass: 'p-anchored-overlay-enter-active', leaveToClass: 'hidden', leaveActiveClass: 'p-anchored-overlay-leave-active', hideOnOutsideClick: true }"
                        type="button"
                        class="layout-topbar-action layout-topbar-action-highlight"
                    >
                        <i class="pi pi-palette"></i>
                    </button>
                    <AppConfigurator />
                </div>
            </div>

            <button
                class="layout-topbar-menu-button layout-topbar-action"
                v-styleclass="{ selector: '@next', enterFromClass: 'hidden', enterActiveClass: 'p-anchored-overlay-enter-active', leaveToClass: 'hidden', leaveActiveClass: 'p-anchored-overlay-leave-active', hideOnOutsideClick: true }"
            >
                <i class="pi pi-ellipsis-v"></i>
            </button>

            <div class="layout-topbar-menu hidden lg:block">
                <div class="layout-topbar-menu-content">
                    <button type="button" class="layout-topbar-action">
                        <i class="pi pi-calendar"></i>
                        <span>Calendar</span>
                    </button>
                    <button type="button" class="layout-topbar-action">
                        <i class="pi pi-inbox"></i>
                        <span>Messages</span>
                    </button>
                    <button type="button" class="layout-topbar-action">
                        <i class="pi pi-user"></i>
                        <span>Profile</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
