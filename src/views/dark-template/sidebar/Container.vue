<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Christian <span class="light-blue--text text--lighten-3">Pfarher</span>
        </h1>
        <span>
          A challenge-loving FullStack software developer
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'c.pfarher@gmail.com',
            },
            /* {
              name: 'Website',
              icon: 'mdi-web',
              text: 'amirreza.in',
            }, */
            {
              name: 'Birth Date',
              icon: 'mdi-cake-variant',
              text: 'May 31, 1985',
            },
            {
              name: 'Habitation',
              icon: 'mdi-map-marker',
              text: 'Crespo, Entre Ríos, Argentina',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/cpfarher',
              link: 'https://github.com/cpfarher',
            },
            {
              icon: 'mdi-linkedin-box',
              text: 'linkedin.com/in/christian-pfarher',
              link: 'https://www.linkedin.com/in/christian-pfarher',
            },
            {
              icon: 'mdi-twitter',
              text: 'twitter.com/cpfarherIT',
              link: 'https://twitter.com/cpfarherIT',
            }, /*,
            {
              icon: 'mdi-instagram',
              text: 'instagram.com/cpfarher',
              link: 'https://instagram.com/cpfarher',
            }, */
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            {
              icon: 'mdi-bullseye',
              text: 'Getting out of Safe Zone',
            },
            {
              icon: 'mdi-book-open-variant',
              text: 'Learning',
            },
            {
              icon: 'mdi-bike',
              text: 'Cycling',
            },
            {
              icon: 'mdi-image-filter-hdr',
              text: 'Nature',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Hacking Stuffs',
            },
            /* {
              icon: 'mdi-teach',
              text: 'Teaching',
            }, */
            {
              icon: 'mdi-basketball',
              text: 'Sports',
            },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            {
              icon: 'mdi-account-group',
              text: 'Leadership',
            },
            /* {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            }, */
            /* {
              icon: 'mdi-android-debug-bridge',
              text: 'Tickling Bugs!',
            }, */
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text : 'Read English',
              value: 85,
            },
            {
              text : 'Write English',
              value: 70,
            },
            {
              text : 'Speak English',
              value: 50,
            },
            {
              text : 'Spanish (Native)',
              value: 100,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
