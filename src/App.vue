<template>
    <div id="app">
        <div style="margin:0 25%">
            <div class="d-flex">
                <div>
                    <h3>Welcome</h3>
                    <p>{{ content.welcome }}</p>

                    <h5>Contact</h5>
                    <ul class="list-unstyled">
                        <li><a :href="contact.linkedin">LinkedIn</a></li>
                        <li><a :href="contact.github">GitHub</a></li>
                    </ul>
                </div>

                <div>
                    <img
                        src="https://github.com/janmouwes.png?size=100"
                        alt="portrait of Jan"
                        class="rounded-circle shadow"
                    />
                </div>
            </div>
            <div>
                <h3>Projects</h3>
                <p>{{ content.projects }}</p>
                <div class="d-flex flex-wrap justify-content-between">
                    <ProjectCard
                        v-for="proj in projects"
                        class="mb-3"
                        style="width: 225px"
                        :key="proj['title']"
                        :project-title="proj['title']"
                        :description="proj['description']"
                        :url="proj['url']"
                        :source-url="proj['source-url']"
                    />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ProjectCard from './components/ProjectCard.vue'
import projectData from "./content/projects.json"
import contentData from "./content/content.json"
import contactData from "./content/contact.json"

export default {
    name: 'App',
    components: {
        ProjectCard
    },
    data() {
        return {
            projects: projectData,
            content: contentData,
            contact: contactData,
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
