<template>
    <div>
        <h1 class="title">Andrew Canter</h1>
        <div class="summary">
            <p>Focused logician with a strong background in mathematics; efficiently finds solutions to complex issues while
                attending to the details. Seeking a software development position to further utilize and enhance my problem
                solving
                skills.</p>
        </div>
        <v-timeline direction="vertical" id="large-viewport-timeline">
            <v-timeline-item v-for="event in timeline" :icon="event.icon" dot-color="white">
                <v-card class="timeline-section">
                    <v-card-title>
                        <p class="date">{{ event.date }}</p>
                        <h2 class="text-h6">{{ event.place }}</h2>
                    </v-card-title>
                    <v-card-text class="bg-white text--primary">
                        <p>{{ event.description }}</p>
                    </v-card-text>
                </v-card>
            </v-timeline-item>
        </v-timeline>
        <v-timeline direction="vertical" id="small-viewport-timeline" side="end">
            <v-timeline-item v-for="event in timeline" :icon="event.icon" dot-color="white">
                <v-card class="timeline-section">
                    <v-card-title>
                        <p class="date">{{ event.date }}</p>
                        <h2 class="text-h6">{{ event.place }}</h2>
                    </v-card-title>
                    <v-card-text class="bg-white text--primary">
                        <p>{{ event.description }}</p>
                    </v-card-text>
                </v-card>
            </v-timeline-item>
        </v-timeline>
        <div class="skills">
            <h2>Technical Skills</h2>
            <ul>
                <li>Object-Oriented Programming: Java, C#, Dart</li>
                <li>Database Programming: SQL, PostgreSQL, SQLite</li>
                <li>Web Application Development: HTML5, CSS, JavaScript, Spring Boot, Vue.js, OAuth 2.0</li>
                <li>Development Tools & Techniques: Unity, Flutter, Responsive Design, IntelliJ, Visual Studio, Visual
                    Studio Code, Git, Linux Bash, Unit Testing (JUnit), Integration Testing</li>
                <li>Other: Blender 3D Modeling, AutoHotKey, Adobe After Effects, Adobe Premiere Pro, DaVinci Resolve</li>
            </ul>
        </div>
    </div>
</template>
<script>
import config from '../../config.json';

export default {
    name: 'About',
    data() {
        return {
            timeline: config.timeline
        }
    }
}
</script>

<style lang="scss">
.date {
    font-size: 1rem;
}

#small-viewport-timeline {
    display: none;
}

#large-viewport-timeline {
    .timeline-section {
        width: 40vw
    }
}

@media only screen and (max-width: 768px) {
    #large-viewport-timeline {
        display: none;
    }

    #small-viewport-timeline {
        display: grid;

        .timeline-section {
            width: 75vw
        }
    }
}

.title {
    text-align: center;
}
</style>