<template>
  <v-app>
    <v-main>
        <top />
        <about />
        <nuxt />
    </v-main>
  </v-app>
</template>

<script>
import top from '../components/top.vue';
import about from '../components/about.vue';


export default {
  components: {
    top,
    about,
  }
}
</script>

<style>
:root {
  --mainColor: #eaeaea;
  --secondaryColor: #fff;
  --borderColor: #c1c1c1;
  --mainText: black;
  --secondaryText: #4b5156;
  --themeDotBorder: #24292e;
  --previewBg: rgba(251, 249, 243, 0.8);
  --previewShadow: #f0ead6;
}

html,
body {
  margin: 0px;
  padding: 0px;
  scroll-behavior: smooth;
}

body *{
	transition: 0.3s;
}

h1,
h2,
h3,
h4,
h5,
h6,
strong {
  color: var(--mainText);
  font-weight: 500px;
  font-family: "Play", sans-serif;
}

p,
li,
span,
label,
input,
textarea,
.v-list-item__title {
  color: var(--secondaryText);
  font-family: "Roboto Mono", monospace;
}

a {
  text-decoration: none;
  color: #17a2b8;
}

ul {
  list-style-type: none;
}

h1 {
  font-size: 56px;
}
h2 {
  font-size: 36px;
}
h3 {
  font-size: 28px;
}
h4 {
  font-size: 24px;
}
h5 {
  font-size: 20px;
}
h6 {
  font-size: 16px;
}

.v-list {
  background-color: transparent !important;
}

.s1 {
  background-color: var(--mainColor);
  border-bottom: 1px solid var(--borderColor);
  overflow: auto;
  min-height: 10em;
}

.s2{
	background-color: var(--secondaryColor);
}

.hWrap {
  min-height: 10em;
}

.mainWindow {
  background-color: var(--secondaryColor);
  border: 1px solid var(--borderColor);
  border-radius: 5px 5px 0px 0px;
  box-shadow: -1px 1px 3px -1px rgba(0, 0, 0, 0.75);
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-areas:
    "upperNav upperNav"
    "leftCol rightCol";
}

.upperNav {
  grid-area: upperNav;
  border-radius: 5px 5px 0px 0px;
  border-bottom: 1px solid var(--borderColor);
  background-color: var(--mainColor);
}

.leftCol {
  grid-area: leftCol;
  padding-top: 50px;
  padding-bottom: 50px;
}

.rightCol {
  grid-area: rightCol;
  display: grid;
  align-content: center;
  padding-top: 50px;
  padding-bottom: 50px;
}

.dot-circle {
  width: 15px;
  height: 15px;
}

#dot1 {
  color: #fc6058;
}

#dot2 {
  color: #fec02f;
}

#dot3 {
  color: #2aca3e;
}

#profile-picture {
  display: block;
  margin: 0 auto;
  height: 200px;
  width: 200px;
  object-fit: cover;
  border: 2px solid var(--borderColor);
  border-radius: 50%;
}

.theme-dot {
  height: 35px;
  width: 35px;
  border-radius: 50%;
  box-shadow: -1px 1px 3px -1px rgba(0, 0, 0, 0.75);
  margin: 5px;
  border: 2px solid var(--themeDotBorder);
  cursor: pointer;
}

.theme-dot:hover {
  border-width: 5px;
}

#light-mode {
  background-color: #fff;
}

#blue-mode {
  background-color: #192734;
}

#green-mode {
  background-color: #78866b;
}

#purple-mode {
  background-color: #7e4c74;
}

#settingsNote {
  font-size: 12px;
  font-style: italic;
  text-align: center;
}

#preview {
  width: 300px;
  height: 300px;
  border: 1.5px dashed #17a2b8;
  background-color: var(--previewShadow);
  padding: 15px;
  position: relative;
  perspective: 1000px;
}

.corner {
  position: absolute;
}

#corner1 {
  top: -14px;
  left: -8px;
  color: #fec02f;
}

#corner2 {
  top: -14px;
  right: -8px;
  color: #fc6058;
}

#corner3 {
  bottom: -3px;
  right: -8px;
  color: #fec02f;
}

#corner4 {
  bottom: -3px;
  left: -8px;
  color: #2aca3e;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

#preview:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: var(--previewBg);
  display: grid;
  align-content: center;
}

.flip-card-back {
  background-color: var(--previewBg);
  transform: rotateY(180deg);
  display: grid;
  align-content: center;
}

.aboutWrapp {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 100px;
}

.skills {
  justify-content: space-evenly;
  background-color: var(--previewShadow);
}

.social {
  display: grid;
  justify-content: center;
}

.card {
  position: relative;
  border-radius: 10px;
  width: 300px;
  height: 200px;
}

.card .icon {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #f00;
  transition: 0.7s;
  z-index: 1;
}

.card:nth-child(1) .icon {
  background: #0077b5;
}

.card .icon .mdi {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 80px;
  transition: 0.7s;
  color: #fff;
}

.card span {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 80px;
  transition: 0.7s;
  color: #fff;
}

.card .face {
  width: 300px;
  height: 200px;
  transition: 0.5s;
}

.card .face.face1 {
  position: relative;
  background: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1;
  transform: translateY(100px);
}

.card:hover .face.face1 {
  background: #ff0057;
  transform: translateY(0px);
}

.card .face.face1 .content {
  opacity: 1;
  transition: 0.5s;
}

.card:hover .face.face1 .content {
  opacity: 1;
}

.card .face.face1 .content i {
  max-width: 100px;
}

.card .face.face2 {
  position: relative;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  box-sizing: border-box;
  box-shadow: 0px 2px 16px 0px rgba(0, 0, 0, 0.75);
  transform: translateY(-100px);
}

.card:hover .face.face2 {
  transform: translateY(0);
}

.card .face.face2 .content p {
  margin: 0;
  padding: 0;
  text-align: center;
  color: #414141;
}

.card .face.face2 .content h3 {
  margin: 0 0 10px 0;
  padding: 0;
  color: #fff;
  font-size: 24px;
  text-align: center;
  color: #414141;
}

.card a {
  text-decoration: none;
  color: #414141;
}

.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.5;
  position: absolute;
  width: 100%;
}

.v-speed-dial {
  position: fixed !important;
}

@media screen and (max-width: 1200px) {
  .container {
    width: 95%;
  }
}

@media screen and (max-width: 800px) {
  .mainWindow {
    grid-template-columns: 1fr;
    grid-template-areas:
      "upperNav"
      "leftCol"
      "rightCol";
  }

  .rightCol {
    justify-content: center;
  }

  .card {
    height: 400px;
  }
}
</style>