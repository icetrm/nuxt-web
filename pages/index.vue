<script setup lang="ts">

const loading = useState('loading', () => false)

const aboutMe = {
    phone: `xxx-xxx-xxxx`,
    email: `theramed.ice@gmail.com`
};

const educations = [
    {
        id: 1,
        name: `National Institute Of Development Administration.`,
        detail: `Master's Degree in Data Analytics and Data Science.`,
        year: `2022 - Present`,
        color: 'green lighten-1',
    },
    {
        id: 2,
        name: `Suranaree University of Technology.`,
        detail: `Bachelor\'s Degree in Computer Engineering.`,
        year: `2015 - 2019`,
        color: 'grey lighten-1',
    }
];

const experiences = [
    {
        id: 1,
        name: `GmProsoft Co., LTD.`,
        position: `Software Engineer.`,
        details: [
            'Coordinate with customers to gather their requirements.',
            'Create documentation and present instructions on how to use the website.',
            `Front-End: Vue.js(Nuxt.js 2.x.x) Create a website using Element UI(component library) to display data from a RESTful API.`,
            `Back-End: JAVA - Spring boot (2.x.x) Create an API to retrieve data from databases such as Microsoft SQL and Cosmos DB.`,
            `Database: Microsoft SQL.`,
            `Cloud: Microsoft Azure Data Factory, Cosmos DB, Blob Storage and Virtual Machine.
`
        ],
        year: `May 2021 - Feb 2023`,
        color: 'grey lighten-1',
    },
    {
        id: 2,
        name: `Qlovr Co., LTD.`,
        position: `Software Engineer.`,
        details: [
            `Front-End: Vue.js (Nuxt.js 2.x.x) Create the UI components. Flutter Create the UI components.`
        ],
        year: `Aug 2019 - Apr 2021`,
        color: 'grey lighten-1',
    },
];

</script>

<template>
    <div>
        <v-card :loading="loading" class="mx-auto my-12" max-width="50%">
            <template v-slot:loader="{ isActive }">
                <v-progress-linear :active="isActive" color="deep-purple" height="4" indeterminate></v-progress-linear>
            </template>

            <div height="250" class="bg-black">
                <v-avatar color="grey" rounded="0" size="150">
                    <v-img
                        src="https://media.licdn.com/dms/image/D4D03AQE23whrSCL4NQ/profile-displayphoto-shrink_800_800/0/1706774828322?e=1717027200&v=beta&t=6ZjhpB7iQ7_MTwXtFpLpvBtoNUVhrVZpZCer5c1Bs9Y"
                        cover></v-img>
                </v-avatar>
                <v-list-item class="text-white" subtitle="Software Engineer" title="Theramed Boonrod"></v-list-item>
            </div>

            <v-card-item>
                <v-card-title>ABOUT ME</v-card-title>

                <v-card-subtitle>
                    <v-icon color="error" icon="mdi-cellphone" size="small"></v-icon>
                    <span class="mx-1">{{ aboutMe.phone }}</span>
                </v-card-subtitle>
                <v-card-subtitle>
                    <v-icon color="error" icon="mdi-at" size="small"></v-icon>
                    <span class="mx-1">{{ aboutMe.email }}</span>
                </v-card-subtitle>
            </v-card-item>

            <!-- <v-card-text>
                <v-row align="center" class="mx-0">
                    <v-rating :model-value="4.5" color="amber" density="compact" size="small" half-increments
                        readonly></v-rating>

                    <div class="text-grey ms-4">
                        4.5 (413)
                    </div>
                </v-row>

                <div class="my-4 text-subtitle-1">
                    $ • Italian, Cafe
                </div>

                <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
            </v-card-text> -->

            <v-divider class="mx-4 mb-1"></v-divider>

            <v-card-item>
                <v-card-title>EDUCATION</v-card-title>
                <v-timeline align="start" side="end">
                    <v-timeline-item v-for="(education, i) in educations" :key="i" :dot-color="education.color"
                        size="x-small">
                        <template v-slot:opposite>
                            <span><strong class="me-4">{{ education.year }}</strong></span>
                        </template>
                        <div class="d-flex">
                            <div>
                                <strong>{{ education.name }}</strong>
                                <div class="text-caption">
                                    {{ education.detail }}
                                </div>
                            </div>
                        </div>
                    </v-timeline-item>
                </v-timeline>
            </v-card-item>

            <v-divider class="mx-4 mb-1"></v-divider>

            <v-card-item>
                <v-card-title>EXPERIENCE</v-card-title>
                <v-timeline align="start" side="end">
                    <v-timeline-item v-for="(experience, i) in experiences" :key="i" :dot-color="experience.color"
                        size="x-small">
                        <template v-slot:opposite>
                            <span><strong class="me-4">{{ experience.year }}</strong></span>
                        </template>
                        <div class="d-flex">
                            <div>
                                <strong>{{ experience.name }}</strong>
                                <div v-for="(detail, j) in experience.details" :key="j" class="text-caption">
                                    • {{ detail }}
                                </div>
                            </div>
                        </div>
                    </v-timeline-item>
                </v-timeline>
            </v-card-item>


            <v-card-actions>
            </v-card-actions>
        </v-card>
    </div>
</template>