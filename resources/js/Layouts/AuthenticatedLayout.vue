<script setup>
import { ref } from 'vue';
import BreezeApplicationLogo from '@/Components/ApplicationLogo.vue';
import BreezeDropdown from '@/Components/Dropdown.vue';
import BreezeDropdownLink from '@/Components/DropdownLink.vue';
import BreezeNavLink from '@/Components/NavLink.vue';
import BreezeResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';
import { Link } from '@inertiajs/vue3';

const showingNavigationDropdown = ref(false);
</script>

<template>
    <div>
        <div class="min-h-screen bg-gray-100">
            <nav class="bg-gray-700 border-b border-gray-100">
                <!-- Primary Navigation Menu -->
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="flex justify-between h-16">
                        <div class="flex">
                            <!-- Logo -->
                            <div class="shrink-0 flex items-center">
                                <Link :href="route('dashboard')">
                                    <BreezeApplicationLogo
                                        class="block w-auto h-12"
                                    />
                                </Link>
                            </div>

                            <!-- Navigation Links -->
                            <div class="hidden space-x-8 sm:-my-px sm:ms-10 sm:flex">
                                <BreezeNavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                    Inicio
                                </BreezeNavLink>

                                <div class="relative my-auto">
                                    <BreezeDropdown :active="$page.url.startsWith('/procesos')">
                                        <template #trigger>
                                            <span class="inline-flex rounded-md">
                                                <button
                                                    type="button"
                                                    class="inline-flex items-center px-3 py-5 border border-transparent text-sm leading-4 font-medium rounded-md text-white hover:text-gray-300 focus:outline-none transition ease-in-out duration-150"
                                                >
                                                    Procesos

                                                    <svg class="ml-2 -mr-0.5 h-4 w-4" xmlns="http://www.w3.org/2000/svg"
                                                        viewBox="0 0 20 20" fill="currentColor">
                                                        <path fill-rule="evenodd"
                                                            d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                                            clip-rule="evenodd" />
                                                    </svg>
                                                </button>
                                            </span>
                                        </template>

                                        <template #content>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Carga Marcaciones </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Marcaciones </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Tarjeta Marcación </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Horas por Mes </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Horas por Pasantía </BreezeDropdownLink>
                                        </template>
                                    </BreezeDropdown>
                                </div>
                                
                                <div class="relative my-auto">
                                    <BreezeDropdown :active="$page.url.startsWith('/consultas')" >
                                        <template #trigger>
                                            <span class="inline-flex rounded-md">
                                                <button
                                                    type="button"
                                                    class="inline-flex items-center px-3 py-5 border border-transparent text-sm leading-4 font-medium rounded-md text-white hover:text-gray-300 focus:outline-none transition ease-in-out duration-150"
                                                >
                                                    Consultas

                                                    <svg
                                                        class="ms-2 -me-0.5 h-4 w-4"
                                                        xmlns="http://www.w3.org/2000/svg"
                                                        viewBox="0 0 20 20"
                                                        fill="currentColor"
                                                    >
                                                        <path
                                                            fill-rule="evenodd"
                                                            d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                                            clip-rule="evenodd"
                                                        />
                                                    </svg>
                                                </button>
                                            </span>
                                        </template>

                                        <template #content>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Desarrollo Prácticas </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Remuneración de Pasantes </BreezeDropdownLink>
                                        </template>
                                    </BreezeDropdown>
                                </div>

                                <div class="relative my-auto">
                                    <BreezeDropdown :active="$page.url.startsWith('/administracion')">
                                        <template #trigger>
                                            <span class="inline-flex rounded-md">
                                                <button
                                                    type="button"
                                                    class="inline-flex items-center px-3 py-5 border border-transparent text-sm leading-4 font-medium rounded-md text-white hover:text-gray-300 focus:outline-none transition ease-in-out duration-150"
                                                >
                                                    Administración

                                                    <svg
                                                        class="ms-2 -me-0.5 h-4 w-4"
                                                        xmlns="http://www.w3.org/2000/svg"
                                                        viewBox="0 0 20 20"
                                                        fill="currentColor"
                                                    >
                                                        <path
                                                            fill-rule="evenodd"
                                                            d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                                            clip-rule="evenodd"
                                                        />
                                                    </svg>
                                                </button>
                                            </span>
                                        </template>

                                        <template #content>
                                            <BreezeDropdownLink :href="route('pasantes.index')"> Pasantes </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Tipo de Constancias </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Constancias </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Emisores Constancias </BreezeDropdownLink>
                                            <BreezeDropdownLink :href="route('profile.edit')"> Supervisores </BreezeDropdownLink>
                                        </template>
                                    </BreezeDropdown>
                                </div>
                            </div>
                        </div>

                        <div class="hidden sm:flex sm:items-center sm:ms-6">
                            <!-- Settings Dropdown -->
                            <div class="ms-3 relative">
                                <BreezeDropdown :active="$page.url.startsWith('/profile')">
                                    <template #trigger>
                                        <span class="inline-flex rounded-md">
                                            <button
                                                type="button"
                                                class="inline-flex items-center px-3 py-5 border border-transparent text-sm leading-4 font-medium rounded-md text-white hover:text-gray-300 focus:outline-none transition ease-in-out duration-150"
                                            >
                                                {{ $page.props.auth.user.name }}

                                                <svg
                                                    class="ms-2 -me-0.5 h-4 w-4"
                                                    xmlns="http://www.w3.org/2000/svg"
                                                    viewBox="0 0 20 20"
                                                    fill="currentColor"
                                                >
                                                    <path
                                                        fill-rule="evenodd"
                                                        d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                                        clip-rule="evenodd"
                                                    />
                                                </svg>
                                            </button>
                                        </span>
                                    </template>

                                    <template #content>
                                        <BreezeDropdownLink :href="route('profile.edit')"> Perfil </BreezeDropdownLink>
                                        <BreezeDropdownLink :href="route('logout')" method="post" as="button">
                                            Cerrar Sesión
                                        </BreezeDropdownLink>
                                    </template>
                                </BreezeDropdown>
                            </div>
                        </div>

                        <!-- Hamburger -->
                        <div class="-me-2 flex items-center sm:hidden">
                            <button
                                @click="showingNavigationDropdown = !showingNavigationDropdown"
                                class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 focus:outline-none focus:bg-gray-600 focus:text-white transition duration-150 ease-in-out"
                            >
                                <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                                    <path
                                        :class="{
                                            hidden: showingNavigationDropdown,
                                            'inline-flex': !showingNavigationDropdown,
                                        }"
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M4 6h16M4 12h16M4 18h16"
                                    />
                                    <path
                                        :class="{
                                            hidden: !showingNavigationDropdown,
                                            'inline-flex': showingNavigationDropdown,
                                        }"
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M6 18L18 6M6 6l12 12"
                                    />
                                </svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Responsive Navigation Menu -->
                <div
                    :class="{ block: showingNavigationDropdown, hidden: !showingNavigationDropdown }"
                    class="sm:hidden"
                >
                    <div class="pt-2 pb-3 space-y-1">
                        <BreezeResponsiveNavLink :href="route('dashboard')" :active="route().current('dashboard')">
                            Inicio
                        </BreezeResponsiveNavLink>
                    </div>

                    <!-- Responsive Settings Options -->
                    <div class="pt-4 pb-1 border-t text-gray-300 border-gray-200">
                        <div class="px-4">
                            <div class="font-medium text-base">
                                {{ $page.props.auth.user.name }}
                            </div>
                        </div>

                        <div class="mt-3 space-y-1">
                            <BreezeResponsiveNavLink :href="route('profile.edit')" :active="$page.url.startsWith('/profile')"> Profile </BreezeResponsiveNavLink>
                            <BreezeResponsiveNavLink :href="route('logout')" method="post" as="button">
                                Log Out
                            </BreezeResponsiveNavLink>
                        </div>
                    </div>
                </div>
            </nav>

            <!-- Page Heading -->
            <header class="bg-white dark:bg-gray-500" v-if="$slots.header">
                <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
                    <slot name="header" />
                </div>
            </header>

            <!-- Page Content -->
            <main>
                <slot />
            </main>
        </div>
    </div>
</template>
