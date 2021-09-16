<template>
      <div class="s1" >
      <v-container>
        <v-row class="hWrap justify-center align-center text-center" id="top">
          <v-col>
            <h1>Hi, I'm Nemanja Galbinovic</h1>
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
</template>

<script>
export default {
    data: () => ({
        theme: localStorage.getItem('root')
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
}
</script>

<style>

</style>