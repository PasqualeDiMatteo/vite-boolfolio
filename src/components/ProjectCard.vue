<script>
export default {
    props: { project: Object, isDetail: Boolean },
    methods: {
        getBgcolor(color) {
            return "bg-" + color;
        }
    }
}
</script>
<template>
    <div class="card">
        <img v-if="project.image" :src="project.image" :alt="project.title" class="img-fluid">
        <div class="card-body ">
            <h4>{{ project.title }}<span :class="getBgcolor(technology.color)" class="badge rounded-pill ms-1"
                    v-for="technology in project.technologies" :key="technology.id">
                    {{ technology.label }}
                </span></h4>
            <p class="card-text">{{ project.description }}</p>
            <a :href="project.url" class="btn btn-primary">Vai su GitHub</a>
            <div class=" mt-3" v-if="project.type">Tipo: {{ project.type.label }}</div>
        </div>
        <div class="card-footer" v-if="!isDetail">
            <router-link :to="{ name: 'detail-page', params: { id: project.id } }" class="btn btn-primary">Vai al
                Dettaglio
            </router-link>
        </div>
    </div>
</template>
<style scoped>
.badge {
    font-size: 0.9rem;
}
</style>