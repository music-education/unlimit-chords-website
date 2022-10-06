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
        <h1>Greg Davies - Software Developer</h1>
        <br>
        <p>This portfolio was made using Ionic Vue 3 and Node.js</p>
        <br>
        <br>
        <br>
        <br>
        <ion-button fill="clear" color="dark" target="_blank" rel="noopener noreferrer" href="https://github.com/gregdavies91">
        <ion-icon :icon="logoGithub" size="large"></ion-icon>
        </ion-button>
        <ion-button fill="clear" color="dark" target="_blank" rel="noopener noreferrer" href="https://uk.linkedin.com/in/gregdavies91">
        <ion-icon :icon="logoLinkedin" size="large"></ion-icon>
        </ion-button>
              
      </div>

    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonToolbar, IonIcon, IonButton } from '@ionic/vue';
import { defineComponent } from 'vue';
import { logoGithub, logoLinkedin } from 'ionicons/icons';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonToolbar,
    IonIcon,
    IonButton
  },
  setup () {
    return {
      logoGithub,
      logoLinkedin
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