<template>
  <v-navigation-drawer app v-if="visible.footer">
    <v-list-item>
      <v-list-item-content>
        <v-list-item-title class="text-h6">Vue-Project</v-list-item-title>
        <v-list-item-subtitle>{{name}}님 환영합니다. </v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense nav>
      <v-list-item v-for="(item, key) in menuList" :key="key" :to="item.path" v-show="item.meta.display">
        <v-list-item-icon>
          <v-icon>{{ item.meta.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.name }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-list-item @click="logout">
        <v-list-item-icon>
          <v-icon>logout</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>logout</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import {mapGetters, mapActions} from "vuex";

export default {
  data: () => ({
    
  }),

  computed : {  
    ...mapGetters('page', ['menuList', 'visible']),
    ...mapGetters('user', ['name'])
  },

  methods : {

    logout(){
      // 로그아웃을 구현하세요.
    }
  }

};
</script>
