<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-searchbar color="medium" @ionChange="sendText"></ion-searchbar>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
      <ListUsers :text="search"/>
    </ion-content>
  </ion-page>
</template>

<script>
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent,IonSearchbar } from '@ionic/vue';
import ListUsers from '@/components/ListUsers.vue';

export default  defineComponent({
  name: 'Tab1Page',
  components: { ListUsers, IonHeader, IonToolbar, IonTitle, IonContent, IonPage,IonSearchbar },
  data(){
    return {
      search: null,
    }
  },
  methods:{
    sendText(event){
      this.search = event.target.value.toLowerCase();
      console.log(this.search)
    }
  },
  
});
</script>
