<template>
  <v-app>
    <div class="s1" >
      <v-container>
        <v-row class="hWrap justify-center align-center text-center" id="top">
          <v-col>
            <h1>Hi, i'm Nemanja Galbinovic</h1>
          </v-col>
        </v-row>

        <v-row class="mainWindow">
          <v-col class="upperNav d-flex justify-space-between" cols="12">
            <div class="d-flex p-10">
              <span
                id="dot1"
                class="mdi mdi-24px mdi-ghost dot-circle mr-2"
              ></span>
              <span
                id="dot2"
                class="mdi mdi-24px mdi-ghost dot-circle mr-2"
              ></span>
              <span id="dot3" class="mdi mdi-24px mdi-ghost dot-circle"></span>
            </div>
            <ul class="m-0 p-10">
              <li class="d-inline-block mr-1 ml-1">
                  <span id="dot2" class="mdi mdi-24px mdi-pac-man"></span>
              </li>
            </ul>
          </v-col>

          <v-col class="leftCol">
            <v-img
              id="profile-picture"
              :src="require('../assets/nemanja.png')"
            ></v-img>
            <h5 class="text-center my-3">Personalize Theme</h5>
            <div class="d-flex justify-center">
              <div id="light-mode" class="theme-dot" @click="theme = ''"></div>
              <div id="blue-mode" class="theme-dot" @click="theme = 'blue'"></div>
              <div id="green-mode" class="theme-dot" @click="theme = 'green'"></div>
              <div id="purple-mode" class="theme-dot" @click="theme = 'purple'"></div>
            </div>
            <p id="settingsNote">
              *Theme settings will be saved for<br />your next visit
            </p>
          </v-col>

          <v-col class="rightCol ml-3">
            <div id="preview">
              <span id="corner1" class="mdi mdi-pac-man corner"></span>
              <span id="corner2" class="mdi mdi-ghost dot-circle corner"></span>
              <div class="flip-card-inner">
                <div class="flip-card-front">
                  <h3>What I Do</h3>
                  <p id="settingsNote">*Hover me*</p>
                </div>
                <div class="flip-card-back">
                  <p>
                    I'm pursuing the opportunity to begin my career in the web
                    development industry.
                  </p>
                </div>
              </div>
              <span id="corner3" class="mdi mdi-ghost dot-circle corner"></span>
              <span id="corner4" class="mdi mdi-ghost dot-circle corner"></span>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <section class="s2" id="aboutme">
      <v-container>
        <div class="aboutWrapp py-12">
          <div class="about">
            <h4 class="mb-5">More about me</h4>
            <p>
              I'm a final year college student interested in Full-stack or
              Front-end positions with the main emphasis on Js technologies.
            </p>

            <p>
              Looking for a place where i can learn and improve my knowledge.
            </p>

            <hr>

            <h4 class="my-5">Familiar with</h4>
            <div class="skills d-flex">
              <v-list>
                <v-list-item v-for="(item, i) in items" :key="i">
                  <v-icon v-text="item.icon" class="mr-1" :color="item.color"></v-icon>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>

              <v-list>
                <v-list-item v-for="(item, i) in items2" :key="i">
                  <v-icon v-text="item.icon" class="mr-1" :color="item.color"></v-icon>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </div>
          </div>
          <div class="social">
            <div class="card">
              <div class="face face1">
                <div class="content">
                  <div class="icon">
                    <span class="mdi mdi-linkedin"></span>
                  </div>
                </div>
              </div>
              <div class="face face2">
                <div class="content">
                  <h3>
                    <a
                      href="https://www.linkedin.com/in/galbinovic584/"
                      target="_blank"
                      >_galbinovic584
                    </a>
                  </h3>
                </div>
              </div>
            </div>
          </div>
        </div>
      </v-container>
    </section>

    <section class="s1" id="projects">
      <h3 class="text-center mt-7">Some of my past projects</h3>
      <p class="text-center">
        *All of them have explanations with gif or pictures on how it looks or
        works in Readme
      </p>
      <v-container>
        <v-row dense>
          <v-col v-for="card in cards" :key="card.id">
            <v-hover v-slot="{ hover }">
              <div class="postW">
              <v-card class="mx-auto my-12" max-width="374" :height="card.h">
                <template slot="progress">
                  <v-progress-linear
                    color="deep-purple"
                    height="10"
                    indeterminate
                  ></v-progress-linear>
                </template>
                <v-img height="290px" :src="card.src">
                  <a :href="card.github" target="_blank">
                    <v-fade-transition>
                      <div
                        v-if="hover"
                        class="
                          d-flex
                          transition-fast-in-fast-out
                          blue-grey
                          darken-1
                          v-card--reveal
                          text-h1
                        "
                        style="height: 100%"
                      >
                        <span
                          class="mdi mdi-github"
                          style="color: #fafafa"
                        ></span>
                      </div>
                    </v-fade-transition>
                  </a>
                </v-img>
                <v-card-title v-text="card.title"></v-card-title>

                <v-card-text>
                  <div v-text="card.text"></div>
                </v-card-text>

                <v-divider class="mx-4"></v-divider>
                <v-card-text>
                  <v-chip-group column>
                    <v-chip v-for="n in card.chip" :key="n" v-text="n"></v-chip>
                  </v-chip-group>
                </v-card-text>
              </v-card>
              </div>
            </v-hover>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <v-speed-dial
      v-model="fab"
      :top="top"
      :bottom="bottom"
      :right="right"
      :left="left"
      :direction="direction"
      :open-on-hover="hover"
      :transition="transition"
    >
      <template v-slot:activator>
        <v-btn v-model="fab" color="blue darken-2" dark fab small>
          <v-icon v-if="fab"> mdi-close </v-icon>
          <v-icon v-else> mdi-cursor-default-click </v-icon>
        </v-btn>
      </template>
      <a href="mailto:galbinovic584@gmail.com">
      <v-btn fab dark small color="#22577A">
        <v-icon>mdi-microsoft-outlook</v-icon>
      </v-btn>
      </a>
      <a href="#projects">
      <v-btn fab dark small color="green">
        <v-icon>mdi-microsoft-visual-studio-code</v-icon>
      </v-btn>
      </a>
      <a href="#aboutme">
      <v-btn fab dark small color="indigo">
        <v-icon>mdi-information-outline</v-icon>
      </v-btn>
      </a>
      <a href="#top">
      <v-btn fab dark small color="red">
        <v-icon>mdi-arrow-up-bold</v-icon>
      </v-btn>
      </a>
    </v-speed-dial>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    direction: "top",
    fab: false,
    fling: false,
    hover: false,
    tabs: null,
    top: false,
    right: true,
    bottom: true,
    left: false,
    transition: "slide-y-reverse-transition",
    theme: localStorage.getItem('root'),
    items: [
      { text: "HTML", icon: "mdi-language-html5", color: '#E54C21' },
      { text: "CSS", icon: "mdi-language-css3", color: '#2965F1' },
      { text: "JavaScript", icon: "mdi-language-javascript", color: 'orange' },
      { text: "Node.js", icon: "mdi-nodejs" , color: 'green' },
    ],
    items2: [
      { text: "Vuetify", icon: "mdi-vuetify" , color: '#7BC6FF' },
      { text: "Nuxt.js", icon: "mdi-nuxt" , color: '#00C58E' },
      { text: "Bootstrap", icon: "mdi-bootstrap" , color: '#7309F5' },
      { text: "MySQL", icon: "mdi-database" , color: 'light-blue' },
    ],
    cards: [
      {
        id: 1,
        title: "NiCat",
        src: require("../assets/projects/nicat.png"),
        github:
          "https://github.com/littlenines/NiCat-HTML-CSS-Project-AppsTeam.git",
        text: "This was my first project that was given to me by my college, the goal was to test my basic HTML and CSS knowledge on a static page.",
        chip: ["HTML", "CSS"],
        h: "505px",
      },
      {
        id: 2,
        title: "BizLand",
        src: require("../assets/projects/bizland.png"),
        github: "https://github.com/littlenines/bootstrap-BizLab.git",
        text: "My second college project where the main emphasis was Bootstrap and it's grid as well as @media for smaller devices.",
        chip: ["HTML", "CSS", "Bootstrap"],
        h: "505px",
      },
      {
        id: 3,
        title: "Spotify Player",
        src: require("../assets/projects/player.png"),
        github: "https://github.com/littlenines/SpotifyPlayer.git",
        text: "Personal project where i wanted to build a player similar to spotify as well as remind myself how audio tag works end learn how to customize controls.",
        chip: ["HTML", "CSS", "JavaScript"],
        h: "505px",
      },
      {
        id: 4,
        title: "Notes",
        src: require("../assets/projects/notes.png"),
        github: "https://github.com/littlenines/Notes-App.git",
        text: "Sticky notes project with marked text where the main goal was to learn how to work with local storage and better understand JavaScript.",
        chip: ["HTML", "CSS", "JavaScript"],
        h: "505px",
      },
      {
        id: 5,
        title: "Final Fantasy XV Weapon List",
        src: require("../assets/projects/ffxv.png"),
        github:
          "https://github.com/littlenines/nuxt-vuetify-FFXV-weapons-list.git",
        text: "In this project the main emphasis was learning Nuxt.js and Vuetify as well as Vue.js",
        chip: ["Nuxt.js", "Vuetify", "Vue.js", "CRUD"],
        h: "505px",
      },
      {
        id: 6,
        title: "Tip Calculator",
        src: require("../assets/projects/tip.png"),
        github: "https://github.com/littlenines/nuxt-vuetify-TipCalculator.git",
        text: "This project was firstly done with Bootstrap and redone with Vuetify in Nuxt to see and understand some differences as well as similarities.",
        chip: ["Nuxt.js", "Vuetify", "Vue.js"],
        h: "505px",
      },
      {
        id: 7,
        title: "Food Order/Admin Panel",
        src: require("../assets/projects/first.png"),
        github: "https://github.com/littlenines/FoodOrder-AdminPanel.git",
        text: "Food ordering project with admin panel, mostly done to showcase and learn how to work with MySQL Stored Procedures.",
        chip: [
          "Bootstrap",
          "Node.js",
          "Express",
          "MySQL",
          "Handlebars",
          "CRUD",
        ],
        h: "550px",
      },
      {
        id: 8,
        title: "Popular Movies API",
        src: require("../assets/projects/movieapi.png"),
        github: "https://github.com/littlenines/apiMovies.git",
        text: "Project for learning how to work with API , tried both Axios and Fetch but sticked with Axios.",
        chip: ["Bootstrap", "Node.js", "Express", "Handlebars", "API"],
        h: "550px",
      },
      {
        id: 9,
        title: "Trello Clone",
        src: require("../assets/projects/trello.png"),
        github: "https://github.com/littlenines/trello-clone.git",
        text: "One of the projects that helped me most in learning Nuxt.js as well as Vuetify and Vue.js. Learned how to use NuxtLink and Layouts with Pages",
        chip: ["Nuxt.js", "Vuetify", "Vue.js", "Firebase"],
        h: "550px",
      },
      {
        id: 10,
        title: "JChat",
        src: require("../assets/projects/chat.png"),
        github: "https://github.com/littlenines/nodejs-JChat.git",
        text: "One of my college projects where i wanted to try something new so i used Socket.io, it was quiet fun learning on how to build a real-time chat app.",
        chip: ["Node.js", "Socket.io", "MongoDB", "Express"],
        h: "550px",
      },
      {
        id: 11,
        title: "Jokes API",
        src: require("../assets/projects/joke.png"),
        github: "https://github.com/littlenines/JokeAPI.git",
        text: "Dad jokes API , first API project where i wanted to understand how it actually works using fetch.",
        chip: ["Node.js", "API", "Express"],
        h: "550px",
      },
      {
        id: 12,
        title: "Portfolio",
        src: require("../assets/projects/portfolio.png"),
        github: "https://github.com/littlenines/JokeAPI.git",
        text: "I wanted to showcase some of my projects easier instead of just sending GitHub links , would be bothersome for people viewing them.",
        chip: ["Nuxt.js", "Vuetify", "Vue.js","Heroku"],
        h: "550px",
      },
    ],
    activeFab: [{ color: "success", icon: "mdi-share-variant" }],
  }),
    mounted: function() {
    this.root = document.documentElement;
    
  },
  watch: {
    theme: {
      handler: function() {
        // because we are using this handler immideatly we need to wait for data changes using nextTick.
        this.$nextTick(() => {
          if (this.theme === 'blue') {
            this.root.style.setProperty("--mainColor", "#15202B");
            this.root.style.setProperty("--secondaryColor", "#192734");
            this.root.style.setProperty("--borderColor", "#164D56");
            this.root.style.setProperty("--mainText", "#fff");

            this.root.style.setProperty("--secondaryText", "#eeeeee");
            this.root.style.setProperty("--themeDotBorder", "#FFF");
            this.root.style.setProperty("--previewBg", "rgb(25, 39, 52, 0.8)");
            this.root.style.setProperty("--previewShadow", "#111921");
            
          } 
          else if(this.theme === 'green'){
            this.root.style.setProperty("--mainColor", "#606B56");
            this.root.style.setProperty("--secondaryColor", "#515a48");
            this.root.style.setProperty("--borderColor", "#161914");
            this.root.style.setProperty("--mainText", "#fff");

            this.root.style.setProperty("--secondaryText", "#eeeeee");
            this.root.style.setProperty("--themeDotBorder", "#FFF");
            this.root.style.setProperty("--previewBg", "rgb(81, 90, 72, 0.8)");
            this.root.style.setProperty("--previewShadow", "#2a2f25");
          
          }
          else if(this.theme === 'purple'){
            this.root.style.setProperty("--mainColor", "#46344E");
            this.root.style.setProperty("--secondaryColor", "#382a3f");
            this.root.style.setProperty("--borderColor", "#1d1520");
            this.root.style.setProperty("--mainText", "#fff");

            this.root.style.setProperty("--secondaryText", "#eeeeee");
            this.root.style.setProperty("--themeDotBorder", "#FFF");
            this.root.style.setProperty("--previewBg", "rgb(29, 21, 32, 0.8)");
            this.root.style.setProperty("--previewShadow", "#2b202f");
           
          }
          else {
            this.root.style.setProperty("--mainColor", "#eaeaea");
            this.root.style.setProperty("--secondaryColor", "#fff");
            this.root.style.setProperty("--borderColor", "#c1c1c1");
            this.root.style.setProperty("--mainText", "black");

            this.root.style.setProperty("--secondaryText", "#4b5156");
            this.root.style.setProperty("--themeDotBorder", "#24292e");
            this.root.style.setProperty("--previewBg", "rgba(251, 249, 243, 0.8)");
            this.root.style.setProperty("--previewShadow", "#f0ead6");
       
          }
        })
         localStorage.setItem('root', this.theme);
      },
      immediate: true
    }
  }
};
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
  position: fixed;
}

.postW {
  display: grid;
  grid-template-columns: repeat(auto-fit, 370px);
  justify-content: center;

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