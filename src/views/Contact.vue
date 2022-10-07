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
    
      <div id="formcontainer">
        <h2>Contact</h2>
        <p>Please send us a message and we'll get back to you</p>
        <form action="https://formsubmit.co/feb45c732c4a51d92e1d721ecaf0c184" method="POST">
          <ion-list>
            <ion-item>
              <ion-label>Name: </ion-label> 
              <ion-input name="name" type="text" color="dark" placeholder="Enter your name..." v-model="state.name"></ion-input>
            </ion-item>
            
            <ion-item>
              <ion-label>Email: </ion-label>
              <ion-input name="email" color="dark" placeholder="Enter your email..." v-model="state.email"></ion-input>
              <span v-if="v$.email.$error">{{ v$.email.$errors[0].$message }}</span>    
            </ion-item>

            <ion-item>
              <ion-textarea name="message" color="dark" placeholder="Write your message here..." v-model="state.message"></ion-textarea>
            </ion-item>

        </ion-list>
        
        <ion-button @click="submitForm" type="submit" expand="block" size="large" color="light">Submit</ion-button>
        <input type="hidden" name="_subject" value="Unlimit Chords user!">
        <input type="hidden" name="_next" value="http://chords.unlimit.co.uk">
        <input type="hidden" name="_captcha" value="false">
        </form>
      </div>

    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonToolbar, IonLabel, IonInput, IonTextarea, IonItem, IonList } from '@ionic/vue';
import { defineComponent, reactive, computed } from 'vue';
import useValidate from '@vuelidate/core';
import { required, email, minLength } from '@vuelidate/validators';

export default defineComponent({
  name: 'Contact',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonToolbar,
    IonLabel,
    IonInput,
    IonTextarea,
    IonItem,
    IonList 
  },
  setup() {
    const state = reactive({
      name: '',
      email: '',
      message: '',
    })
    const rules = computed(() => {
      return {
        name: { required, minLength: minLength(2) },
        email: { required, email },
      }
    })

    const v$ = useValidate(rules, state)

    // const result = ref(null)

    // axios.get('../views/Contact.vue')
    //   .then(data => result.value = data);

    return {
      state,
      v$,
      // result
    }
  },
  methods: {
    submitForm() {
      console.log('Form Values', this.state)

      this.v$.$validate()
      if (!this.v$.$error) {
        alert('Form sucessfully submitted. I will get back to you shortly.')
      }
      else {
        alert('Error! Please fill in all the required fields and click submit again.')
      }    
    }
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