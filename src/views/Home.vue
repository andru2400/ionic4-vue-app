<template>
  
 <ion-card>
   
    <ion-item>
      <ion-label position="floating">Escriba nombre: </ion-label>
      <ion-input :value="greeting" @input="greeting = $event.target.value"></ion-input>
    </ion-item>
        <ion-button expand="full" color="secondary" v-on:click="oneClick" href="#">Enviar</ion-button>        
  
  </ion-card>
</template>

<script>
export default {
  data() {
    return {
      greeting: ""
    };
  },
  methods: {
    // oneClick() {
    //   this.$ionic.alertController
    //     .create({
    //       header: "Alerta",
    //       subHeader: "Sub Alerta",
    //       message: "Hola mundo",
    //       buttons: ["ok"]
    //     })
    //     .then(a => a.present());
    // }
    async oneClick() {
      const alert = await this.$ionic.alertController.create({
        header: "Alerta",
        subHeader: "Sub Alerta",
        message: this.greeting,
        buttons: ["ok"]
      });
      await alert.present();
    }
  }
};
</script>
