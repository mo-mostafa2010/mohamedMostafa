<template>
<v-container>
    <h3 class="text-center title mt-8" data-aos="fade-up">Skills</h3>
    <div class="text-center">
        <v-card v-for="skill in skills" :data-aos="skill.animation" :key="skill.title" class="skillCard mb-2">
            <v-card-title class="indigo--text">{{skill.title}}</v-card-title>
            <v-chip v-for="tech in skill.technologies" :key="tech.name" class="ma-2" :color="tech.color" text-color="white">
                {{tech.name}}
            </v-chip>
        </v-card>
    </div>
</v-container>
</template>

<script>
export default {
    data() {
        return {
            msg: 'hello',
            skills: [{
                    title: 'Front-end Development',
                    animation: 'zoom-in-up',
                    technologies: [{
                            name: 'Vue js',
                            color: '#41b883'
                        },
                        {
                            name: 'Nuxt js',
                            color: '#2f495e'
                        },
                        {
                            name: 'VueX',
                            color: '#41b883'
                        },
                        {
                            name: 'TypeScript',
                            color: '#0077c6'
                        },
                        {
                            name: 'Vuetify',
                            color: '#1867c0'
                        },
                        {
                            name: 'SASS',
                            color: '#cd6799'
                        },
                        {
                            name: 'Mocha js',
                            color: '#8d6748'
                        },
                        {
                            name: 'd3 js',
                            color: '#f69d4b'
                        },
                        {
                            name: 'chart js',
                            color: '#fe777b'
                        }
                    ],
                },
                {
                    title: 'Back-end Development',
                    animation: 'zoom-in-down',
                    technologies: [{
                            name: 'Node js',
                            color: '#333'
                        },
                        {
                            name: 'PHP - Basic knowledge',
                            color: '#7773b3'
                        },
                        {
                            name: 'EXPRESS JS',
                            color: '#ecd91c'
                        },
                        {
                            name: 'MYSQL',
                            color: '#de8a00'
                        }
                    ],
                },
                {
                    title: 'MATLAB',
                    animation: 'zoom-in-right',
                    technologies: [{
                            name: 'Image Processing',
                            color: '#35749d'
                        },
                        {
                            name: 'Error Detection & Correction',
                            color: 'indigo'
                        },
                    ],
                },
                {
                    title: 'Others',
                    animation: 'zoom-in-right',
                    technologies: [{
                            name: 'Python',
                            color: '#366d9e'
                        },
                        {
                            name: 'Embedded Systems - Basic Knowledge',
                            color: '#555555'
                        },
                        {
                            name: 'Unity 3d - game development',
                            color: '#000000'
                        },
                    ],
                },
            ]
        }
    },
}
</script>

<style lang="scss" scoped>
.skillCard {
    // border: 1px indigo solid;
}
</style>
