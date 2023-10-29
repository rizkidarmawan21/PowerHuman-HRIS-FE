<template>
    <div class="flex flex-col gap-4">
        <div class="text-sm text-grey">
            {{ title }}
        </div>

        <SidebarItem v-for="(data, index) in items" :key="index" :title="data.title" :icon="data.icon" :url="data.url" :active="data.active" />
    </div>
</template>

<script>
export default {
    name: 'SidebarItemGroup',
    props: {
        title: {
            type: String,
            default: ''
        },
        items: {
            type: Array,
            default: () => []
        },
    }
}

</script>