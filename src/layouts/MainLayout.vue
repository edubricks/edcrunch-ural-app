<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-dark" bordered>
      <q-toolbar>

        <q-btn
          class="lt-md"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-space class="lt-md"/>
        <q-btn
          flat
          dense
          round
          icon="home"
        />
        <q-space class="gt-sm" />
        <q-tabs class="gt-sm" inline-label no-caps>
          <q-route-tab
            icon="event_note"
            to="/"
            exact
            label="Мероприятия"
          />
          <q-route-tab
            icon="alarm"
            to="/"
            exact
            label="Участникам"
          />
          <q-route-tab
            icon="supervisor_account"
            to="/"
            exact
            label="Спикеры"
          />
          <q-route-tab
            icon="description"
            to="/"
            exact
            label="Публикации"
          />
        </q-tabs>
        <q-space/>
        <q-btn
          flat
          round
          icon="account_circle"
        />
      </q-toolbar>
      <q-tabs inline-label no-caps>
        <q-route-tab
          icon="event_note"
          to="/"
          exact
          label="Track#1"
        />
        <q-route-tab
          icon="event_note"
          to="/"
          exact
          label="Track#1"
        />
        <q-route-tab
          icon="event_note"
          to="/"
          exact
          label="Track#1"
        />
        <q-route-tab
          icon="event_note"
          to="/"
          exact
          label="Track#1"
        />
        <q-route-tab
          icon="event_note"
          to="/"
          exact
          label="Track#1"
        />
      </q-tabs>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      side="left"
      behavior="normal"
      overlay
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink';

export default {
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Docs',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev',
        },
        {
          title: 'Github',
          caption: 'github.com/quasarframework',
          icon: 'code',
          link: 'https://github.com/quasarframework',
        },
        {
          title: 'Discord Chat Channel',
          caption: 'chat.quasar.dev',
          icon: 'chat',
          link: 'https://chat.quasar.dev',
        },
        {
          title: 'Forum',
          caption: 'forum.quasar.dev',
          icon: 'record_voice_over',
          link: 'https://forum.quasar.dev',
        },
        {
          title: 'Twitter',
          caption: '@quasarframework',
          icon: 'rss_feed',
          link: 'https://twitter.quasar.dev',
        },
        {
          title: 'Facebook',
          caption: '@QuasarFramework',
          icon: 'public',
          link: 'https://facebook.quasar.dev',
        },
      ],
    };
  },
};
</script>
