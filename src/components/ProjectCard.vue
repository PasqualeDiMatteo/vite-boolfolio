<script>
export default {
    props: { project: Object }
}
</script>
<template>
    <div class="card mt-5">
        <img v-if="project.image" :src="project.image" :alt="project.title">
        <div class="card-body">
            <h1>{{ project.title }}</h1>
            <p class="card-text">{{ project.description }}</p>
            <a :href="project.url" class="btn btn-primary">Vai su GitHub</a>
        </div>
    </div>
</template>
<style></style>