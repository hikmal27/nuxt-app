<template>
    <nuxt-link :to="Url">
        <div class="px-3 py-2">
            <p>{{ MenuTitle }}</p>
        </div>
    </nuxt-link>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    props: {
        MenuTitle: {
            type: String,
            required: true
        },
        Url: {
            type: String,
            default: '#'
        }
    }
}
</script>
