<template>
    <ion-page>
      <ion-header :translucent="true">
        <ion-toolbar>
          <ion-title>UvaBomBom</ion-title>
        </ion-toolbar>
      </ion-header>
      
      <ion-content :fullscreen="true">
      {{myfavs}}
        <ion-list>
          <ion-item-sliding v-for = "cancion in lista" :key= "cancion.id">
            <ion-item>
              <ion-label>{{cancion.name}}</ion-label>
            </ion-item>
            <ion-item-options side="start">
              <ion-item-option @click="Like(cancion)">
                <ion-icon v-if="cancion.isFav" src="/assets/svg/trash.svg"></ion-icon>
                <ion-icon v-else src="/assets/svg/heart.svg"></ion-icon>
              </ion-item-option>
            </ion-item-options>
            <ion-item-options side="end">
              <ion-item-option @click="Delete(cancion)">Eliminar</ion-item-option>
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
  IonToolbar,
  IonIcon } from '@ionic/vue';
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
    IonIcon,
  },

  data () {
    return{ 
        lista : [
          { id: 1, name: 'Moscow Mule', isFav: false},
          { id: 2, name: 'Despues de la playa', isFav: false},
          { id: 3, name: 'Me porto bonito', isFav: false},
          { id: 4, name: 'Titi me pregunto', isFav: false},
          { id: 5, name: 'JGL', isFav: false},
          { id: 6, name: 'Matitas verdes', isFav: false},
          { id: 7, name: 'Hublot', isFav: false},
          { id: 8, name: 'Sagre de reyes', isFav: false},
          { id: 9, name: 'El ansioso', isFav: false},
          { id: 10, name: 'Sangolotiadito', isFav: false},
          { id: 11, name: 'La boda del huitlacoche', isFav: false},
          { id: 12, name: 'El uno', isFav: false},
          { id: 13, name: 'El 21', isFav: false},
          { id: 14, name: '300 Locos', isFav: false},
          { id: 15, name: 'Tú', isFav: false},
          { id: 16, name: 'El piyi', isFav: false},
          { id: 17, name: 'Descuido del aguila', isFav: false},
          { id: 18, name: 'EL chihuas', isFav: false},
          { id: 19, name: 'Pearl Harbor', isFav: false},
          { id: 20, name: 'Botones azules', isFav: false},
        ],
        myfavs : []

    }
  },

  methods : {
    Like : function(element) {
      if (!element.isFav){
        this.myfavs.push(element.name);
        element.isFav = true;
      }
      else{
        this.myfavs = this.myfavs.filter(item => item !== element.name);
        element.isFav = false;
      }
    }
  }

});
</script>