<script setup lang="ts">
const { $notion } = useNuxtApp();
const { data } = await useAsyncData("notion-index", () =>
  $notion.getPageBlocks("677dcadf924c4cdcae3198c047c18245")
);
const { mapPageUrl, pageLinkOptions } = useProps();
</script>

<template>
  <div>
    <NotionRenderer
      :blockMap="data"
      fullPage
      prism
      katex
      :mapPageUrl="mapPageUrl"
      :pageLinkOptions="pageLinkOptions"
    />
  </div>
</template>
