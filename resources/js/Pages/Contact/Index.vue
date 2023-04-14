<template>
    <Head title="Dashboard" />

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Contact
            </h2>
            <Swal ref="swal" :errors="$page.props.errors" :flash="$page.props.flash" />

        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <div class="mb-4">
                            <Link
                                class="
                                    px-6
                                    py-2
                                    mb-2
                                    text-green-100
                                    bg-green-500
                                    rounded
                                "
                                :href="route('contact.create')"
                            >
                                 Create Contact
                            </Link>
                        </div>
                        <table>
                            <thead class="font-bold bg-gray-300 border-b-2">
                                <td class="px-4 py-2">name</td>
                                <td class="px-4 py-2">phone</td>
                                <td class="px-4 py-2">email</td>
                                <td class="px-4 py-2">Action</td>
                            </thead>
                            <tbody>
                                <tr v-for="contact in contact.data" :key="contact.id">
                                    <td class="px-4 py-2">{{ contact.name }}</td>
                                    <td class="px-4 py-2">{{ contact.phone }}</td>
                                    <td class="px-4 py-2">
                                        {{ contact.email }}
                                    </td>
                                    <td class="px-4 py-2 font-extrabold">
                                        <Link
                                            class="text-green-700"
                                            :href="route('contact.edit', contact.id)"
                                        >
                                           Details
                                        </Link>
                                        <!-- <Link
                                            @click="destroy(contact.id)"
                                            class="text-red-700"
                                            >Delete</Link
                                        > -->
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                        <pagination :links="contact.links" />
                    </div>
                </div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>

<script>
import BreezeAuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import BreezeNavLink from "@/Components/NavLink.vue";
import { Head } from "@inertiajs/inertia-vue3";
import { Link } from "@inertiajs/inertia-vue3";
import Swal from "@/Components/Swal.vue";

export default {
    components: {
        BreezeAuthenticatedLayout,
        Head,
        BreezeNavLink,
        Link,
        Swal,
    },
    props: {
        contact: Object,
    },
    // methods: {
    //     destroy(id) {
    //         this.$inertia.delete(route("contact.destroy", id));
    //     },
    // },
};
</script>