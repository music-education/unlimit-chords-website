<template>
  <ion-page>

<ion-header>
      <ion-toolbar style="--background: transparent">

<!--   This button has to be on all views, can it be in a component? -->
        <ion-button fill="clear" slot='start' style="--background-hover-opacity: 0%">
          <ion-menu-button color="dark" style="--background-hover-opacity: 0%"></ion-menu-button>
        </ion-button>

      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
    
      <div id="container">
        <h1>Unlimit Chords</h1>
        <br>
        <p>Play any chord on the guitar</p>
        <br>
        <br>
        <ion-label><p>Download Test Flight App</p></ion-label>
        <ion-button fill="clear" color="dark" target="_blank" rel="noopener noreferrer" href="https://apps.apple.com/us/app/testflight/id899247664">
        <ion-icon :icon="download" size="large" label="Download Test Flight App"></ion-icon>
        </ion-button>
        <br>
        <ion-label><p>Download Unlimit Chords BETA</p></ion-label>
        <ion-button fill="clear" color="dark" target="_blank" rel="noopener noreferrer" href="itms-beta://testflight.apple.com/join/uIanyIEK">
        <ion-icon :icon="download" size="large"></ion-icon>
        </ion-button>
              
      </div>

    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonToolbar, IonIcon, IonButton, IonLabel } from '@ionic/vue';
import { defineComponent } from 'vue';
import { download } from 'ionicons/icons';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonToolbar,
    IonIcon,
    IonButton,
    IonLabel
  },
  setup () {
    return {
      download
    }
  }
});
</script>

<style>
ion-content {
  font-family: Office Code Pro !important;
  font-size: 1.2em;
}
#container {
  text-align: center;
  
  position: absolute;
  left: 75px;
  right: 75px;
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