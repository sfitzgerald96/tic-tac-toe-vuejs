# Intro to Vue.js

## About
This is a project for my Web Dev class at BYU. I created a video introducing some of the basics of Vuejs. In the video I recreate the tic-tac-toe app that the React tutorial uses, but do it in Vuejs. Below is the URL to the YouTube video. 

Youtube Tutorial Video URL: 

## Agenda of Video
1. Compare Vue.js with React
2. Introduction to Vue Instance
3. Template Components
4. Recreate the Tic-tac-toe React app

## References of Resources Used in Video
Vue.js Lifecycle Diagram: https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram

Vue.js API Reference: https://vuejs.org/v2/api/

Vue.js Why Vue doesn't pass functions to children components: https://michaelnthiessen.com/pass-function-as-prop/

## Notes
Vue prefers Templates vs Render functions in Virtual DOM

Can access render functions directly though

Vue.js doesn't pass functions down as props, they use events to fire up to the parent instead
- In addition, when an event goes back up to the root Vue instance you have to say @click.native

Different ways to run Vuejs. Either with a CDN or downloaded library directly or through templating

Vuejs can't track direct mutation of arrays or objects, so you need to splice a brand new one for it to rerender