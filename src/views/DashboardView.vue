<script lang="ts" setup>
import { ref } from "vue";

import PrimeDataTable, { type DataTableProps } from '@/components/prime/PrimeDataTable.vue';
const tableConfig: Partial<DataTableProps> = {
    paginator: true,
    rows: 2,
    resizableColumns: true,
    columnResizeMode: "expand",
    scrollable: true,
    scrollHeight: "400px",
};
const columns = [
    { field: "id", header: "ID", frozen: true },
    { field: "name", header: "Name" },
    { field: "data 1", header: "Data 1" },
    { field: "data 2", header: "Data 2" },
    { field: "data 3", header: "Data 3" },
    { field: "data 4", header: "Data 4" },
    { field: "data 5", header: "Data 5" },
    { field: "data 6", header: "Data 6" },
    { field: "email", header: "Email" }
];
const lines = [
    { id: 1, name: "John Doe", email: "john.doe@example.com" },
    { id: 2, name: "Jane Smith", email: "jane.smith@example.com" },
    { id: 3, name: "Alice Johnson", email: "alice.johnson@example.com" },
];

import PrimeDialog from '@/components/prime/PrimeDialog.vue';
const openModal = () => {
    modalRef.value?.openModal("Custom Header"); // You can pass a custom header
};
const handleActionCompleted = (result: any) => {
    console.log("Action completed:", result);
};
const modalRef = ref<InstanceType<typeof PrimeDialog>>();
</script>
<template>
    <div class="grid">
        <h1>This is Dashboard View.</h1>
        <div class="col-12">
            <div class="card">
                <PrimeDataTable :configuration="tableConfig" :columns="columns" :lines="lines" />
            </div>
        </div>
        <div class="col-12">
            <Button label="Open Modal" icon="pi pi-external-link" @click="openModal" />
        </div>
    </div>
    <PrimeDialog ref="modalRef" @action-completed="handleActionCompleted" />
</template>