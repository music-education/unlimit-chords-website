<template>
  <ion-page>

    <ion-header>
      <ion-toolbar style="--background: transparent">

<!--         This button has to be on all views, can it be in a component? -->
        <ion-button fill="clear" background="transparent" slot='start'>
          <ion-menu-button color="dark"></ion-menu-button>
        </ion-button>
        
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <div id="container">

        <h1>Page Not Found</h1>

          <router-link to="/about">
            <ion-button color="light">Go Back Home</ion-button>
          </router-link>

      </div>
    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageNotFound',
  components: {
    IonContent,
    IonHeader,
    IonPage,
  }
  
});
</script>

<style>
ion-content, ion-input, ion-label, ion-button, ion-textarea {
  font-family: Office Code Pro !important;
  font-size: 1.2em;
}
#formcontainer {
  text-align: center;
  margin: auto;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  max-width: 600px;
}

@media (max-width: 700px) {
  #formcontainer {
    left: 50px;
    right:  50px;
  }
}

#formcontainer strong {
  font-size: 20px;
  line-height: 26px;
}

#formcontainer p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#formcontainer a {
  text-decoration: none;
}
</style>