<template>
    <ion-header>
      <ion-toolbar>
        <ion-title>Inline Modal</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-button id="open-modal" expand="block">Open</ion-button>
      <p>{{ message }}</p>
      <ion-modal ref="modal" trigger="open-modal" @willDismiss="onWillDismiss">
        <ion-header>
          <ion-toolbar>
            <ion-buttons slot="start">
              <ion-button @click="cancel()">Cancel</ion-button>
            </ion-buttons>
            <ion-title>Welcome</ion-title>
            <ion-buttons slot="end">
              <ion-button :strong="true" @click="confirm()">Confirm</ion-button>
            </ion-buttons>
          </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding custom-class">
          <ion-item>
            <ion-label position="stacked">Enter your name 1</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 2</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 3</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 4</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 5</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 6</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 7</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 8</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 9</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 10</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 11</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 12</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 13</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 14</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 15</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item> 
          <ion-item>
            <ion-label position="stacked">Enter your name 16</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 17</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 18</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 19</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
          <ion-item>
            <ion-label position="stacked">Enter your name 20</ion-label>
            <ion-input ref="input" type="text" placeholder="Your name"></ion-input>
          </ion-item>
        </ion-content>
      </ion-modal>
    </ion-content>
  </template>


<script lang="ts">
  import {
    IonButtons,
    IonButton,
    IonModal,
    IonHeader,
    IonContent,
    IonToolbar,
    IonTitle,
    IonItem,
    IonInput,
    IonLabel,
  } from '@ionic/vue';
  import { OverlayEventDetail } from '@ionic/core/components';
  import { defineComponent, ref } from 'vue';

  export default defineComponent({
    name: 'ModalView',
    components: {
      IonButtons,
      IonButton,
      IonModal,
      IonHeader,
      IonContent,
      IonToolbar,
      IonTitle,
      IonItem,
      IonInput,
      IonLabel,
    },
    data() {
      return {
        message: 'This modal example uses triggers to automatically open a modal when the button is clicked.',
      };
    },
    methods: {
      cancel() {
        (this.$refs.modal as any).$el.dismiss(null, 'cancel');
      },
      confirm() {
        const name = (this.$refs.modal as any).$el.value;
        (this.$refs.modal as any).$el.dismiss(name, 'confirm');
      },
      onWillDismiss(ev: CustomEvent<OverlayEventDetail>) {
        if (ev.detail.role === 'confirm') {
          this.message = `Hello, ${ev.detail.data}!`;
        }
      },
    },
  });
</script>

<style>
.custom-class {
    height: 90%;
}
</style>