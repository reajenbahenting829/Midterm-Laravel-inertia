<template layout>
    <div class="flex justify-between">
        <h1>Members List</h1>
    </div>
    <hr />
    <Link href="/members/create" class="btn bg-indigo-800 hover:bg-indigo-900 float-right mt-5 mb-4"
        >Add Member</Link
    >
    <div class="py-4">
        <table class="table mt-3">
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Last Name</th>
                    <th>First Name</th>
                    <th>Designation</th>
                    <th>Company Member</th>
                    <th>Action</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="member of members" :key="member.id">
                    <td>{{ member.id }}</td>
                    <td>{{ member.last_name }}</td>
                    <td>{{ member.first_name }}</td>
                    <td>{{ member.designation }}</td>
                    <td>{{ member.company.name }}</td>
                    <td>
                        <Link
                            :href="'/members/edit/' + member.id"
                            class="btn bg-sky-600 hover:bg-sky-700"
                        >
                            Edit
                        </Link>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/inertia-vue3";

defineProps({
    members: Array,
});
</script>
