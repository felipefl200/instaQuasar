<template>
  <q-page class="constrain q-pa-md">
    <div class="row q-col-gutter-lg">
      <div class="col-12 col-sm-8">
        <q-card v-for="post in posts" :key="post.id" class="card-post q-mb-md" flat bordered>
          <q-item>
            <q-item-section avatar>
              <q-avatar>
                <img src="https://gravatar.com/avatar/2658ad33f14f5f6d2d326d6fa5f3dd92">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-bold">Felipe França</q-item-label>
              <q-item-label caption>
                {{post.location}}
              </q-item-label>
            </q-item-section>
          </q-item>

          <q-separator/>

          <q-img
            :src="post.imageUrl"
          />

          <q-card-section>
            <div class="text-h6">{{post.caption}}</div>
            <div class="text-caption text-grey">{{ post.date | niceDate }}</div>
          </q-card-section>


        </q-card>
      </div>
      <div class="col-4 large-screen-only">
        <q-item class="fixed">
          <q-item-section avatar>
            <q-avatar size="3rem">
              <img src="https://gravatar.com/avatar/2658ad33f14f5f6d2d326d6fa5f3dd92">
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label class="text-bold">Felipe França</q-item-label>
            <q-item-label caption>
              Porto Alegre
            </q-item-label>
          </q-item-section>
        </q-item>
      </div>
    </div>

  </q-page>
</template>

<script>
    import {date} from 'quasar'

    export default {
        name: 'PageHome',
        data() {
            return {
                posts: [
                    {
                        id: 1,
                        caption: 'Parque Farroupilha',
                        date: '1598545084059',
                        location: 'Porto Alegre',
                        imageUrl: 'http://www.ospa.org.br/wp-content/uploads/2017/11/parque-da-redencao.jpg',

                    },
                    {
                        id: 2,
                        caption: 'Parque Marinha',
                        date: '1598549087059',
                        location: 'Porto Alegre',
                        imageUrl: 'https://www.guiadoesporte.com/wp-content/uploads/cache/images/Parque-Marinha-do-Brasil-Porto-Alegre-RS-e1472764051631/Parque-Marinha-do-Brasil-Porto-Alegre-RS-e1472764051631-2369614533.jpg',

                    },
                    {
                        id: 3,
                        caption: 'Gasometro',
                        date: '1598543587059',
                        location: 'Porto Alegre',
                        imageUrl: 'http://lproweb.procempa.com.br/pmpa/prefpoa/smc/usu_img/Usina_JoelVargas_03.jpg',

                    },
                    {
                        id: 4,
                        caption: 'Gasometro Porto Alegre',
                        date: '1598544045510',
                        location: 'Porto Alegre',
                        imageUrl: 'https://i.pinimg.com/originals/5e/c5/35/5ec535eb781fff2b9b1dfb60fb1743e2.jpg',

                    }
                ]
            }
        },
        filters: {
            niceDate(value) {
                if (!value) return ''

                return date.formatDate(parseFloat(value), 'DD, MMMM YYYY HH:mm')
            }
        }
    }
</script>

<style lang="sass">
  .card-post
    .q-img
      min-height: 200px
</style>
