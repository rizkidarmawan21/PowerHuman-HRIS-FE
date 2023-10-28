<template>
    <NuxtLink :to="url" class="nav-link" :class="[{ 'active': active }]">
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