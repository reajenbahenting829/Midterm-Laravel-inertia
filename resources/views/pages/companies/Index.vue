<template layout>
    <div class="flex justify-between">
        <h1>Companies List</h1>
    </div>
    <hr />
    <Link href="/companies/create" class="btn bg-indigo-800 hover:bg-indigo-900 float-right mt-5 mb-4"
        >Add Company</Link
    >
    <table class="table mt-5">
        <thead>
            <tr>
                <th>ID</th>
                <th>Company Name</th>
                <th>Type</th>
                <th>Address</th>
                <th>Net Worth</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="company in companies" :key="company.id">
                <td>{{ company.id }}</td>
                <td>{{ company.name }}</td>
                <td>{{ company.type }}</td>
                <td>{{ company.address }}</td>
                <td>
                    {{
                        parseFloat(company.net_worth).toLocaleString(
                            undefined,
                            {
                                minimumFractionDigits: 2,
                                maximumFractionDigits: 2,
                            }
                        )
                    }}
                </td>
                <td>
                    <Link
                        :href="'/companies/edit/' + company.id"
                        class="btn bg-sky-600 hover:bg-sky-700"
                    >
                        Edit
                    </Link>
                </td>
            </tr>
        </tbody>
    </table>
</template>

<script setup>
import { Link } from "@inertiajs/inertia-vue3";
defineProps({
    companies: Array,
});
</script>
