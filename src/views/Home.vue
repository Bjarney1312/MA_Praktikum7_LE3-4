<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Rechner</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content>
      <ion-item>
        <ion-label position="stacked">Zahl 1</ion-label>
        <ion-input type="number" name="zahl1" v-model.number="zahl1"></ion-input>
      </ion-item>

      <ion-item>
       <ion-label position="floating">Zahl 2</ion-label>
       <ion-input type="number" name="zahl2" v-model.number="zahl2"></ion-input>
      </ion-item>
      <ion-button @click="berechne">Berechne</ion-button>

      <ion-item>
       <ion-label position="floating">Ergebnis</ion-label>
       <ion-input type="number" v-model="ergebnis" disabled></ion-input>
      </ion-item>
    </ion-content>

    <ion-footer>
      <ion-toolbar>
        <ion-title>Footer</ion-title>
      </ion-toolbar>
  </ion-footer>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonToolbar, IonFooter, IonHeader, IonTitle, IonContent, IonButton, IonActionSheet, IonItem, IonLabel, IonInput } from '@ionic/vue';
import { Options, Vue } from 'vue-class-component';
import { 
  caretForwardCircle, 
  close,
  heart, 
  trash,
  share 
} from 'ionicons/icons';

@Options({
  components: {
    IonPage, IonToolbar, IonFooter, IonHeader, IonTitle, IonContent, IonButton, IonActionSheet, IonItem, IonLabel, IonInput
  },
})
export default class Home extends Vue {

  public zahl1: number = 10;
  public zahl2: number = 2;
  public ergebnis: number = 0;

  public mounted(): void {
    console.log("mounted");
  }

  public berechne(): void {
    this.ergebnis = this.zahl1 + this.zahl2;
    console.log("typeof(zahl1)=" + typeof(this.zahl1));
    console.log("typeof(zahl2)=" + typeof(this.zahl2));
    console.log("typeof(ergebnis)=" + typeof(this.ergebnis));
    console.log(this.zahl1 + " + " + this.zahl2 + " = " + this.ergebnis);
  }
  
}
</script>

<style lang="scss">
.my-custom-class {
  --background: #ace768;
}
</style>