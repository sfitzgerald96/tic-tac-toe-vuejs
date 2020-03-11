# Intro to Vue.js

## About
This is a project for my Web Dev class at BYU. I have created a video introducing some of the basics of Vuejs. Since my class is focusing on React development, I have recreated the tic-tac-toe app in Vue to effectively compare the basics of React to Vuejs
Below is the URL to the YouTube video. 

Youtube Tutorial Video URL:

## Agenda of Video
1. Compare Vue.js with React
    - Look at website's comparison
2. Introduction to Vue Instance
    - Options
    - API reference
3. Template Components
    - Directives
    - Template
    - Script
    - Style
4. Recreate the Tic-tac-toe React app
    - Vue-CLI
    - Managing state (data)
    - Props
    - Child to Parent Communication
    - Lists

## References of Resources Used in Video
- Vue.js vs React comparison https://vuejs.org/v2/guide/comparison.html
- Vue.js Documentation: https://vuejs.org/v2/guide/
- Vue.js API Reference: https://vuejs.org/v2/api/

## Notes
Vue prefers Templates vs Render functions in Virtual DOM

Can access render functions directly though

Vue.js doesn't pass functions down as props, they use events to fire up to the parent instead
- In addition, when an event goes back up to the root Vue instance you have to say @click.native

Different ways to run Vuejs. Either with a CDN or downloaded library directly or through templating

Vuejs can't track direct mutation of arrays or objects, so you need to splice a brand new one for it to rerender

Style tags can be scoped `<style scoped>` which makes them scoped to the component