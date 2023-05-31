<script setup>
defineProps({
  row: Array
})
</script>

<template>
  <tr>
    <td class="name">{{ row[0] }}</td>
    <td class="details">{{ row[1] }}</td>
    <td class="link">
      <a :href="row[2]" target="_blank">Link</a>
    </td>
    <td class="rating">{{ row[3] }}</td>
  </tr>
</template>
