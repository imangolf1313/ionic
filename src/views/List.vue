<template>
    <ion-page>
      <ion-header :translucent="true">
        <ion-toolbar>
          <ion-title>UvaBomBom</ion-title>
        </ion-toolbar>
      </ion-header>
      
      <ion-content :fullscreen="true">
        <ion-list>
          <ion-item-sliding v-for = "cancion in lista" :key= "cancion.id">
            <ion-item>
              <ion-label>{{cancion.name}}</ion-label>
            </ion-item>
            <ion-item-options side="end">
              <ion-item-option @click="Like(item)">Me Gusta</ion-item-option>
            </ion-item-options>
          </ion-item-sliding>
        </ion-list>
      </ion-content>
    </ion-page>
    <!-- <div>
        <h1>Holaa {{ejemplo}}</h1>
        <input type="text" name="ejemplo" v-model="ejemplo">
    </div> -->
</template>

<script>
import {
  IonContent,
  IonLabel,
  IonList, 
  IonItem,
  IonItemOption, 
  IonItemOptions, 
  IonItemSliding,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ListPage',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonLabel,
    IonList, 
    IonItem,
    IonItemOption, 
    IonItemOptions, 
    IonItemSliding,
  },

  data () {
    return{ 
        lista : [
          { id: 1, name: 'Moscow Mule'},
          { id: 2, name: 'Despues de la playa'},
          { id: 3, name: 'Me porto bonito'},
          { id: 4, name: 'Titi me pregunto'},
          { id: 5, name: 'JGL'},
          { id: 6, name: 'Matitas verdes'},
          { id: 7, name: 'Hublot'},
          { id: 8, name: 'Sagre de reyes'},
          { id: 9, name: 'El ansioso'},
          { id: 10, name: 'Sangolotiadito'},
          { id: 11, name: 'La boda del huitlacoche'},
          { id: 12, name: 'El uno'},
          { id: 13, name: 'El 21'},
          { id: 14, name: '300 Locos'},
          { id: 15, name: 'Tú'},
          { id: 16, name: 'El piyi'},
          { id: 17, name: 'Descuido del aguila'},
          { id: 18, name: 'EL chihuas'},
          { id: 19, name: 'Pearl Harbor'},
          { id: 20, name: 'Botones azules'},
        ],
    }
  }

});
</script>