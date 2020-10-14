<template>
    <card class="flex flex-col items-center justify-center p-6" :class="this.style">
        <template v-if="html">
            <div v-html="html"></div>
        </template>
        <template v-else>
            <h1 class="text-3xl font-light" v-text="this.title"></h1>
            <h2 class="text-base font-light" v-text="this.subtitle"></h2>
        </template>
    </card>
</template>

<script>
export default {
    props: ['title', 'subtitle', 'theme', 'hover', 'html'],
    computed: {
        style() {
            return [
                this.theme.background,
                this.theme.text,
                'hover:' + this.hover.background,
                'hover:' + this.hover.text,
            ]
        }
    }
}
</script>
