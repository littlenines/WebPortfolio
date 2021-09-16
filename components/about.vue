<template>
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
</template>

<script>
export default {
data: () => ({
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
})
}
</script>

<style>

</style>