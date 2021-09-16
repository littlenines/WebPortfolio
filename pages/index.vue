<template>
  <v-app>
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
  layout: 'default',
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
        github: "https://github.com/littlenines/WebPortfolio.git",
        text: "I wanted to showcase some of my projects easier instead of just sending GitHub links , would be bothersome for people viewing them.",
        chip: ["Nuxt.js", "Vuetify", "Vue.js","Heroku"],
        h: "550px",
      },
    ],
    activeFab: [{ color: "success", icon: "mdi-share-variant" }],
  }),
};
</script>

<style>

</style>