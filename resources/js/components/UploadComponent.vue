<template>
<v-app id="keep">
    <v-content class="grey lighten-4">
    <v-app-bar
      app
      clipped-left
    >
        <!-- <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon> -->
        <v-toolbar-title class="title ml-3 mr-5" href="/">Imagemap</v-toolbar-title>
        <v-spacer></v-spacer>
        <template >
            <v-btn icon>
                <v-icon>mdi-export-variant</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>mdi-delete-circle</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>mdi-plus-circle</v-icon>
            </v-btn>
        </template>
      
    </v-app-bar>

    <!-- <v-navigation-drawer
      v-model="drawer"
      app
      clipped
      color="grey lighten-4"
    >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            v-if="item.heading"
            :key="i"
            align-center
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
          </v-layout>
          <v-divider
            v-else-if="item.divider"
            :key="i"
            dark
            class="my-4"
          ></v-divider>
          <v-list-item
            v-else
            :key="i"
            
          >
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="grey--text">
                {{ item.text }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer> -->

    
      <v-container
        fluid
        fill-height
        class="grey lighten-4"
        grid-list-md text-center
      >
        <v-layout
            wrap
          justify-center
          align-center
        >
          <v-flex shrink xs6 class="one">
            <v-card color="blue-grey" dark tile flat>
              <v-card-text>{{ lorem }}</v-card-text>
            </v-card>
          </v-flex>
          <v-flex shrink xs6 class="two">
            <v-card color="brown" dark tile flat>
              <v-card-text>{{ lorem }}</v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
      items: [
        { heading: 'Labels' },
        { divider: true },
        { icon: 'mdi-anchor', text: 'Notes' },
        { icon: 'mdi-anchor', text: 'Reminders' },
        { icon: 'mdi-anchor', text: 'Create new label' },
        
        
      ],
       lorem: `Lorem ipsum dolor sit amet, mel at clita quando. Te sit oratio vituperatoribus, nam ad ipsum posidonium mediocritatem, explicari dissentiunt cu mea. Repudiare disputationi vim in, mollis iriure nec cu, alienum argumentum ius ad. Pri eu justo aeque torquatos.`,
    }),
}
</script>
<style>
#keep .v-navigation-drawer__border {
  display: none
}
</style>