<script setup lang="ts">
import { useLayout } from '@/layout/composables/layout';
import { computed } from 'vue';

const { layoutConfig } = useLayout();

</script>

<template>
    <div class="layout-footer">
        <span class="font-medium ml-2">
            Prime Sakai Template
        </span>
    </div>
</template>
<style lang="scss" scoped></style>
