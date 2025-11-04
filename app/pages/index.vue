<script setup lang="ts">
const items = ref([
  { label: 'Circle', value: 'circle', icon: 'i-ph-circle' },
  { label: 'Triangle', value: 'triangle', icon: 'i-ph-triangle' },
  { label: 'Square', value: 'square', icon: 'i-ph-square' },
])
</script>

<template>
  <div>
    <UPage>
      <template #left>
        <UPageAside>
          <URadioGroup class="ml-2" indicator="hidden" variant="card" default-value="circle" :items="items">
            <template #label="{ item }">
              <div class="flex items-center">
                <UIcon :name="item.icon" class="size-5 mr-2" />
                <span>{{ item.label }}</span>
              </div>
            </template>
          </URadioGroup>
        </UPageAside>
      </template>

      <UPageBody />
    </UPage>
  </div>
</template>
