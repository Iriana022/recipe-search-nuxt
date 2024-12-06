<template>

    <div class="grid">
        <article v-if="props.instructions">
            <header>
                <h5>Preparations</h5>
            </header>
            <p>
                {{ props.instructions }}
                <br>
                <NuxtLink :to="props.video" v-if="props.video">
                    See video
                </NuxtLink>
            </p>
        </article>
        
    </div>
</template>

<script setup>
    const props = defineProps({
        instructions: String,
        video: String
    })
</script>