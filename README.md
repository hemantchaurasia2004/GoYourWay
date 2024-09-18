# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh


  

  
# Trip Planner App :earth_africa:	:mountain_snow:

<div style="text-align: center;"> 
 
## :star: Building a Fullstack AI Trip Planner with React, Gemini AI, TailwindCSS & Firebase
 


## Firebase Configuration

```javascript
// firebase.js
import firebase from 'firebase/app';
import 'firebase/auth';
import 'firebase/firestore';

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};

firebase.initializeApp(firebaseConfig);
const auth = firebase.auth();
const db = firebase.firestore();

export { auth, db };
```

## Environment Variables

```bash
REACT_APP_GOOGLE_API_KEY=your-google-api-key
REACT_APP_GEMINI_API_KEY=your-gemini-api-key
```

## Google Authentication

```javascript
firebase.auth().signInWithPopup(googleProvider)
  .then((result) => {
    const user = result.user;
    // Handle user session
  })
  .catch((error) => {
    console.error("Error during login: ", error);
  });
```

## Generate Trip (Gemini AI)

```javascript
fetch('/generateTrip', {
  method: 'POST',
  body: JSON.stringify({ budget, destination, duration, interests }),
  headers: { 'Content-Type': 'application/json' },
})
.then(response => response.json())
.then(data => {
  // Handle itinerary generation
})
.catch(error => {
  console.error('Error generating trip: ', error);
});
```

## Autocomplete (Google Places API)

```javascript
fetch(`/placesAutocomplete?input=${destination}`)
  .then(response => response.json())
  .then(data => {
    // Handle autocomplete suggestions
  })
  .catch(error => {
    console.error('Error fetching autocomplete: ', error);
  });
```

## Save Itinerary (Firebase Firestore)

```javascript
firebase.firestore().collection('itineraries').add({
  userId: user.uid,
  itinerary: itineraryData
})
.then(() => {
  console.log("Itinerary saved!");
})
.catch((error) => {
  console.error("Error saving itinerary: ", error);
});
```


# You can check app this link :point_down:

## Setup .env file
### :key: Environment Variables


```js
VITE_GOOGLE_PLACES_API_KEY
VITE_GOOGLE_GEMINI_AI_API_KEY
VITE_GOOGLE_AUTH_CLIENT_ID
``` 

