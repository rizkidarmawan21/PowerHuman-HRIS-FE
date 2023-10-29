<template>
    <!-- Sidebar -->
    <div class="hidden lg:block fixed lg:max-w-[295px] w-full overflow-y-auto h-full bg-white z-[999]" id="sidebarHRIS">
        <div class="px-6 py-[50px] gap-y-[50px] flex flex-col">
            <div class="flex items-center justify-between">
                <a href="#" class="flex justify-center">
                    <img src="/assets/svgs/logo-type.svg" alt="">
                </a>
                <a href="#" id="toggleCloseSidebar" class="lg:hidden">
                    <svg class="w-6 h-6 text-dark" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12">
                        </path>
                    </svg>
                </a>
            </div>

            <SidebarItemGroup v-for="(data, index) in sidebarItem" :key="index" :items="data.items" :title="data.title" />

        </div>
    </div>
</template>

<script>
export default {
    name: 'Sidebar',
    data() {
        return {
            sidebarItem: [
                {
                    title: 'Daily Use',
                    items: [
                        {
                            title: `Overview`,
                            icon: '/assets/svgs/ic-grid.svg',
                            active: this.$route.fullPath.split('/')[1] == '' ? true : false,
                            url: 'companies-id'
                        },
                        {
                            title: 'Employees',
                            icon: '/assets/svgs/ic-users.svg',
                            active: this.$route.fullPath.split('/')[1] == 'employes' ? true : false,
                            url: 'companies-id-employes'
                        },
                        {
                            title: 'My Teams',
                            icon: '/assets/svgs/ic-briefcase.svg',
                            active: this.$route.fullPath.split('/')[1] == 'teams' ? true : false,
                            url: 'companies-id-teams'
                        },
                        {
                            title: 'Roles',
                            icon: '/assets/svgs/ic-flag.svg',
                            active: this.$route.fullPath.split('/')[1] == 'roles' ? true : false,
                            url: 'companies-id-roles'
                        }
                    ]
                },
                {
                    title: 'Others',
                    items: [
                        {
                            title: 'Insurances',
                            icon: '/assets/svgs/ic-box.svg',
                            active: false,
                            url: '#'
                        },
                        {
                            title: 'Company',
                            icon: '/assets/svgs/ic-home.svg',
                            active: false,
                            url: '#'
                        },
                        {
                            title: 'Rewards',
                            icon: '/assets/svgs/ic-gift.svg',
                            active: false,
                            url: '#'
                        },
                        {
                            title: 'Settings',
                            icon: '/assets/svgs/ic-settings.svg',
                            active: false,
                            url: '#'
                        },
                        {
                            title: 'Logout',
                            icon: '/assets/svgs/ic-signout.svg',
                            active: false,
                            url: '#'
                        }
                    ]
                }
            ]
        }
    },
}
</script>