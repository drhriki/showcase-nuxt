<script setup>
import { ref } from 'vue';
import AppMenuItem from './AppMenuItem.vue';
const model = ref([
    {
        label: 'Home',
        items: [{ label: 'Dashboard', icon: 'pi pi-fw pi-home', to: '/' }]
    },
    {
        label: 'Master Data',
        items: [
            {
                label: 'Branch',
                icon: 'pi pi-fw pi-home',
                to: '/master/branch'
            },
            {
                label: 'Principal',
                icon: 'pi pi-fw pi-id-card',
                to: '/master/principal'
            },
            {
                label: 'Warehouse',
                icon: 'pi pi-fw pi-home',
                to: '/master/warehouse'
            }
        ]
    },
    {
        label: 'Report',
        items: [
            {
                label: 'Report Movement Stock',
                icon: 'pi pi-fw pi-file',
                to: '/report/movementstock'
            }
        ]
    }
]);
</script>

<template>
    <ul class="layout-menu">
        <br />
        <i class="pi pi-user"></i>
        &nbsp;
        <b>Welcome, Riki Hermawan</b>
        <hr />
        <template v-for="(item, i) in model" :key="item">
            <app-menu-item v-if="!item.separator" :item="item" :index="i"></app-menu-item>
            <li v-if="item.separator" class="menu-separator"></li>
        </template>
    </ul>
</template>

<style lang="scss" scoped></style>
