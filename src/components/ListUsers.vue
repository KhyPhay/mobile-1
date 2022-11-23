<template>
  <ion-card>KhyPhay/mobile-1
    <ion-card-header>
      <ion-card-title>Class 2022 A</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      <ion-list>
        <ion-item v-for="user of searchUser" :key="user.img">
          <ion-avatar slot="start">
            <img alt="Silhouette of mountains" src="../images/PHAT_Khy.jpg" />
          </ion-avatar>
          <ion-label>{{user.name}}</ion-label>
        </ion-item>
      </ion-list>
    </ion-card-content>
  </ion-card>
</template>
<script>
import { defineComponent } from 'vue';
import {IonItem, IonList, } from '@ionic/vue';
export default defineComponent({
  components: { IonItem, IonList },
  props: {
    text: String
  },
  data() {
    return {
      users: [
        {name: "Khy Phat",},
        {name: "Savoeurt Pheap",},
        {name: "Tim Bin",},
        {name: "Vibol Khan",},
        {name: "Theavy Vun",},
        {name: "Phearun Chun",},
        {name: "Thib Tik",},
        {name: "Nga Heourn",},
        {name: "Sreyleak El",},
        {name: "Seyha Seurn",},
        {name: "Sarath Orn",},
        {name: "Sopha Rath",},
        {name: "Phandy Porn",},
        {name: "Hak Kim",},
      ],
      userShow: []
    }
  },
  methods: {
  },
  computed: {
    searchUser(){
      if(this.text !== null){
        return this.users.filter(user=> user.name.toLowerCase().search(this.text) >= 0)
      }else{
        return this.users
      }
    },
  },
  mounted(){
    this.userShow = this.users
  }
});
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
