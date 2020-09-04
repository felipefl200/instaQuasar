<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
      class="bg-white text-grey-10"
      bordered>
      <q-toolbar class="constrain">
        <q-btn to="/camera" class="large-screen-only q-mr-xs"
               flat dense round icon="eva-camera-outline" size="1rem"/>
        <q-separator class="large-screen-only" vertical spaced />
        <q-toolbar-title class="text-grand-hotel text-bold">
          Instaclone
        </q-toolbar-title>
        <q-btn to="/" class="large-screen-only"
               flat dense round icon="eva-home-outline" size="1rem"/>
      </q-toolbar>
    </q-header>

    <q-footer bordered class="bg-white small-screen-only">
      <q-tabs active-color="primary"
              indicator-color="transparent"
              class="text-grey-10">
        <q-route-tab to="/" icon="eva-home-outline"/>
        <q-route-tab to="/camera" icon="eva-camera-outline"/>
      </q-tabs>
    </q-footer>

    <q-page-container class="bg-grey-1">
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script>
    export default {
        name: 'MainLayout',
        data() {
            return {}
        }
    }
</script>
<style lang="sass">
  .q-toolbar
    @media (min-width: $breakpoint-sm-min)
     height: 4rem

  .q-toolbar__title
    font-size: 2rem
    @media (max-width: $breakpoint-xs-max)
     text-align: center

    .q-footer
      .q-tab__icon
        font-size: 2rem
</style>
