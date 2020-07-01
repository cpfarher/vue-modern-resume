<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Who am I?"
      >
        I'm a <strong>Full stack Ruby/Ruby on Rails professional developer</strong> born in Argentina with +10 years of expertise in software development.
        Day by day, I try to challenge my self studying the latest technologies and continually improving my skills for get the success on different projects and with teams that I'm part of.
        <br><br>
        As <strong>Engineer</strong> I have the capacity for get efficciently solutions for a variety of problems.
        Throughout my professional career I was work and have developed solutions for different areas such as education, commercial and industrial/factory prduction systems, focusing on providing solutions to end users.<br>
        <br>
        Because I am a full stack developer, I have solid familiarity with all layers of the web stack and capabilities to deploy web systems. On the last 6 year I was working on back end and front end providing professional solutions mainly with <strong>Ruby and Ruby on Rails</strong> and also I do task's of <strong>Devops</strong>.<br>
        <br>
        <i>I have focused on carrying out web projects no only with Ruby / Ruby on Rails, also I have a lot of experience with JS and VueJS, and obviously HTMl and css as the main core tools. As part of the development the gems of ruby, npm, webpack, socket io, personalized APIs among other technologies have become part of the base of many projects that I developed.<br>
          On my working day linux and tools like git, shell, docker and git ci/cd integration are part of my work life.</i>
      </content-section>
      <content-section
        v-if="prouds"
        title="What am I proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <v-switch
        v-model="skillsShowed"
        :label="skillsShowed ? 'Hide Skills' : 'Show detailed skills'"
        class="pull-right"
      />
      <content-section
        v-if="skills && skillsShowed"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    skillsShowed: false,
    prouds      : [
      {
        icon  : 'mdi-leadership',
        text  : 'Leadership software developer group on my starts',
        source: 'ww.unl.edu.ar - UNL (Universidad nacional del litoral)',
      },
      {
        icon  : 'mdi-software',
        text  : 'Semi senior developer on a software factory',
        source: 'https://www.serfe.com/en/',
      },
      {
        icon  : 'mdi-timer-sand',
        text  : 'Full stack Ruby developer and Leadership on ByS Control systems',
        source: 'Different kind of systems for manage and control Industries',
      },
    ],
    educations: [
      {
        from       : '2003',
        to         : '2013',
        title      : 'Bachelor\'s degree, Computer Science Engineering',
        location   : 'Santa Fe, Argentina',
        description: 'Graduated',
      },
      {
        from       : '2003',
        to         : '2012',
        title      : 'Level VIII of English (Upper Intermeidate)',
        location   : 'Santa Fe, Argentina',
        description: 'Language course completed',
      },
      {
        from       : '1998',
        to         : '2002',
        title      : 'BA with job training as an aid in business management',
        location   : 'Entre Ríos, Argentina',
        description: 'High School',
      },
    ],
    skills: [
      {
        title: 'Ruby / Ruby on Rails Framework',
        icon : 'mdi-language-ruby',
        value: 100,
      },
      {
        title: 'JavaScript /ECS6',
        icon : 'mdi-language-javascript',
        value: 100,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 100,
      },
      {
        title: 'CSS / SASS / LESS',
        icon : 'mdi-css',
        value: 100,
      },
      {
        title: 'PostrgreSQL / mysql',
        icon : 'mdi-postgresql',
        value: 85,
      },
      {
        title: 'Redis',
        icon : 'mdi-redis',
        value: 30,
      },
      {
        title: 'MongoDB',
        icon : 'mdi-mongo',
        value: 30,
      },
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 95,
      },
      {
        title: 'CakePHP Framework',
        icon : 'mdi-cake-php',
        value: 90,
      },
      {
        title: 'Drupal',
        icon : 'mdi-drupal',
        value: 20,
      },
      {
        title: 'C/C++',
        icon : 'mdi-language-cpp',
        value: 75,
      },
      { divider: true },
      {
        title: 'Grafana',
        icon : 'mdi-grafana',
        value: 90,
      },
      {
        title: 'Prometheus',
        icon : 'mdi-language-prometheus',
        value: 90,
      },
      {
        title: 'Alert manager',
        icon : 'mdi-alertmanager',
        value: 90,
      },
      { divider: true },
      {
        title: 'Ubuntu Server',
        icon : 'mdi-ubuntu',
        value: 80,
      },
      {
        title: 'Linux',
        icon : 'mdi-linux',
        value: 95,
      },
      {
        title: 'Bash / Scripting',
        icon : 'mdi-bash',
        value: 75,
      },
      /* {
        title: 'Web Application Security',
        icon : 'mdi-shield-lock',
        value: 80,
      }, */
      {
        title: 'Nginx',
        icon : 'mdi-nginx',
        value: 70,
      },
      {
        title: 'Apache',
        icon : 'mdi-apache',
        value: 70,
      },
      {
        title: 'Passenger',
        icon : 'mdi-passenger',
        value: 70,
      },
      /*      {
        title: 'Test Driven Development',
        icon : 'mdi-test-tube',
        value: 26,
      }, */
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 60,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 80,
      },
      {
        title: 'Docker',
        icon : 'mdi-docker',
        value: 90,
      },
      {
        title: 'Docker compose',
        icon : 'mdi-docker-compose',
        value: 90,
      },
      { divider: true },
      /* {
        title: 'Hardware Development',
        icon : 'mdi-chip',
        value: 29,
      }, */
      { divider: true },
      {
        title: 'Leadership',
        icon : 'mdi-account-group',
        value: 70,
      },
      /* {
        title: 'Content Marketing (+340 articles)',
        icon : 'mdi-text',
        value: 96,
      }, */
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
