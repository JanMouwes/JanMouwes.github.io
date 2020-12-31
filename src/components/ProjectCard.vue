<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">{{ this.projectTitle }}</h5>
            <p class="card-text" :active="this.description != null">{{ this.description }}</p>
            <ul class="list-unstyled">
                <li><a :href='this.url' :active="this.url != null">Link</a></li>
                <li><a :href='this.sourceUrl' :active="this.sourceUrl != null">Source</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css"

export default {
    name: "ProjectCard",
    props: {
        projectTitle: {
            type: String,
            required: true
        },
        description: {
            type: String
        },
        url: {
            type: String
        },
        sourceUrl: {
            type: String
        }
    }
}
</script>

<style scoped>
a {
    white-space: nowrap;
    text-overflow: clip;
    display: block;
    overflow: hidden;
}
</style>