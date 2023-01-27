<template>
    <div class="gif" :style="`background-image: url('${gif.images.fixed_width.url}')`"></div>
</template>

<script>
export default {
    name: "Gif",
    props: ['gif'],
}
</script>
