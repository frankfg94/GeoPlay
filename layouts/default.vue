<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>
      <div
        style=" font-size: 1.3em; cursor:pointer"
        @click="$router.push('/homepage')"
      >
        {{ title }}
      </div>
      <v-spacer />
      <ProfileAvatar :user="$store.getters['users/user']" />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-account-circle',
          title: 'Welcome',
          to: '/homepage'
        },
        {
          icon: 'mdi-account-circle',
          title: 'Profile',
          to: '/profile'
        },
        {
          icon: 'mdi-crosshairs-question',
          title: 'Create Quiz',
          to: '/create_quizz'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Geoplay'
    }
  }
}
</script>
