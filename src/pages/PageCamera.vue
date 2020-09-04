<template>
  <q-page class="constrain-more q-pa-md">
    <div class="camera-frame q-pa-md">
      <img class="full-width"
           src="http://www.ospa.org.br/wp-content/uploads/2017/11/parque-da-redencao.jpg" alt="">
    </div>
    <div class="text-center q-pa-md">
      <q-btn color="grey-10" size="lg" icon="eva-camera" round/>
      <div class="row justify-center q-ma-md">
        <q-input v-model="post.caption" class="col col-sm-6" label="Caption" dense/>
      </div>
      <div class="row justify-center q-ma-md">
        <q-input v-model="post.location" class="col col-sm-6" label="Location" dense>
          <template v-slot:append>
            <q-btn round dense color="grey-10" flat icon="eva-pin"/>
          </template>
        </q-input>
      </div>
      <div class="row justify-center q-ma-md q-mt-lg">
        <q-btn rounded unelevated label="Post Image" color="primary"/>
      </div>
    </div>
  </q-page>
</template>

<script>
    import {uid} from 'quasar'

    export default {
        name: 'PageHome',
        data() {
            return {
                post: {
                    id: uid(),
                    caption: '',
                    location: '',
                    photo: null,
                    date: Date.now()
                }
            }
        }
    }
</script>
<style lang="sass">
  .camera-frame
    border: 2px solid $grey-10
    border-radius: 0.4rem
</style>
