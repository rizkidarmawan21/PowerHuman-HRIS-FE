<template>
    <NuxtLink :to="{ name: url }" class="nav-link" :class="[{
        'active': $route.fullPath == url ? true : false,
    }]">
        <img :src="icon">
        {{ title }}
    </NuxtLink>
</template>

<script>
export default {
    name: 'SidebarItem',
    props: {
        title: {
            type: String,
            default: ''
        },
        icon: {
            type: String,
            default: ''
        },
        active: {
            type: Boolean,
            default: false
        },
        url: {
            type: String,
            default: ''
        }
    }
}
</script>