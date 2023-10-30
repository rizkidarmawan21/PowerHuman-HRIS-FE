<template>
    <section class="py-[200px] flex flex-col items-center justify-center px-4">
        <div class="text-[32px] font-semibold text-dark mb-4">Select Companies</div>
        <div class="w-full card">
            <div class="form-group">
                <label for="" class="text-grey">Companies</label>

                <p v-if="$fetchState.pending">Fetching companies...</p>
                <select v-else v-model="selectedCompany" class="appearance-none input-field form-icon-chevron_down">
                    <option value="" disabled selected>Select Company</option>
                    <option :value="data.id" v-for="(data, index) in companies.data.result.data" :key="index">
                        {{ data.name }}
                    </option>
                </select>
            </div>
            <button @click="openCompany" class="w-full btn btn-primary mt-[14px]">
                Continue
            </button>
            <div class="text-center">or</div>
            <NuxtLink :to="{ name: 'companies-create' }" class="w-full border btn btn-white">
                Create New Company
            </NuxtLink>
        </div>
    </section>
</template>
  
<script>
export default {
    middleware: 'auth',
    data() {
        return {
            companies: [],
            selectedCompany: ''
        }
    },
    async fetch() {
        this.companies = await this.$axios.get('/company',)
    },
    methods: {
        openCompany() {
            this.$router.push({ name: 'companies-id', params: { id: this.selectedCompany } })
        }
    }
}
</script>