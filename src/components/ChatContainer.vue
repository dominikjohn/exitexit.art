<template>
  <div>
    <br />
    <Message v-for="message in messages" :key="message.id" :message="message" />
    <Message v-for="message in messages" :key="message.id" :message="message" />
    <Message v-for="message in messages" :key="message.id" :message="message" />
  </div>
</template>

<script>
import Message from './Message'
import {initializeApp} from 'firebase/app';
import {getFirestore, collection, getDocs} from 'firebase/firestore/lite';

const firebaseConfig = {
  apiKey: "AIzaSyBtV4fdasuEOk9BQ7H636wwDw3qBewfNdo",
  authDomain: "projekt-exit.firebaseapp.com",
  projectId: "projekt-exit",
  storageBucket: "projekt-exit.appspot.com",
  messagingSenderId: "491832711530",
  appId: "1:491832711530:web:d2a37800505df3d730ad13"
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

export default {
  components: {Message},
  name: 'ChatContainer',
  data: () => ({
    messages: null,
  }),
  created() {
    const citiesCol = collection(db, 'nachrichten');
    getDocs(citiesCol).then((result) => {
      let unsortedMessages = result.docs.map((data) => {
        return {id: data.id, ...data.data()}
      })
      this.messages =  unsortedMessages.sort((a, b) => {
        return a.zeit.seconds > b.zeit.seconds
      })
    });
  }
}
</script>