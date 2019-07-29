<template>
 <v-layout row>
    <v-flex class="online-users adheight" xs4>
      

    </v-flex>
    
    <v-flex id="privateMessageBox" class="messages mb-5 adheight" xs8>
        <v-tabs :grow=true  >
                <v-tabs-slider></v-tabs-slider>
                <v-tab href="#tab-1">Nature</v-tab>
                <v-tab href="#tab-2">Cars</v-tab>
                <v-tab href="#tab-3">People</v-tab>
                <v-tab-item v-for="i in tabs"
                    :key="i"
                    :value="'tab-' + i">
                    <v-container
                    fluid
                    grid-list-sm
                    >
                    <v-layout wrap>
                        <v-flex
                        v-for="a in 6"
                        :key="a"
                        xs12
                        md4
                        >
                        <!-- <v-img
                            :src="`https://picsum.photos/500/300?image=${a * i * 5 + 10}`"
                            :lazy-src="`https://picsum.photos/10/6?image=${a * i * 5 + 10}`"
                            aspect-ratio="1"
                        ></v-img> -->
                        <v-card>
                        <v-img
                        :src="`https://picsum.photos/500/300?image=${a * i * 5 + 10}`"
                        :lazy-src="`https://picsum.photos/10/6?image=${a * i * 5 + 10}`"
                        aspect-ratio="1"
                        height="200px"
                        >
                        <v-card-title
                            class="fill-height align-end"
                            
                        ></v-card-title>
                        </v-img>

                        <v-card-actions>
                        <v-spacer></v-spacer>

                        <v-btn icon>
                            <v-icon>favorite</v-icon>
                        </v-btn>

                        <v-btn icon>
                            <v-icon>bookmark</v-icon>
                        </v-btn>

                        <v-btn icon>
                            <v-icon>share</v-icon>
                        </v-btn>
                        </v-card-actions>
                    </v-card>
                        </v-flex>
                    </v-layout>
                    </v-container>
                </v-tab-item>
                </v-tabs>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
    props: {
      source: String,
    },
    data: () => ({
        tabs: 3,
        drawer: null,
        items: [
            { heading: 'Labels' },
            { divider: true },
            { icon: 'mdi-anchor', text: 'Notes' },
            { icon: 'mdi-anchor', text: 'Reminders' },
            { icon: 'mdi-anchor', text: 'Create new label' },
        ],
        valid:false,
        lazy: false,
        select: null,
        items: [
            'Item 1',
            'Item 2',
            'Item 3',
            'Item 4',
        ],
    }),
    methods:{
        validate () {
        if (this.$refs.form.validate()) {
          this.snackbar = true
        }
      },
      reset () {
        this.$refs.form.reset()
      },
    }
}
</script>
<style>
#keep .v-navigation-drawer__border {
  display: none
}
</style>