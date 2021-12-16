<template>
  <div class="resume_bg">
      <div class="resume_mid">
          <div class="resume_intro">
              <br/>
              <div class="resume_title">Resume</div>
              <div class="resume_intro_left">
                  <br/><br/>
                  <p class="resume_intro_left_title">Andy Zhang</p>
                  <p class="resume_intro_left_subtitle">Frontend/Full-stack Developer</p>
                  <p class="resume_intro_left_text">Hey guys, I am here!</p>
                  <p class="resume_intro_left_text">{{resumetext1}}</p>
                  <p class="resume_intro_left_text">{{resumetext2}}</p>
              </div>
              <img class="resume_intro_right" :src="require('@/assets/images/img_resume_me.png')" alt=""/>
          </div>
    
          <div class="resume_skills">
              <p class="resume_abilitytitle">Abilities</p>
              <p class="resume_abilitysubtitle">My skills</p>
              <a-row :gutter="[25,25]">
              <div v-for="(item, key) in skills" :key="key">
                  <a-col :span="8">
                  <a-card :title="item.skillname" :bordered="false" class="resume_skilltitle">
                      <div slot="extra" class="resume_skillitemtitle">{{item.percentage}}%</div>
                      <div class="resume_skillitem" :style="{'--resume_skillitem_width': item.percentage, '--resume_skillitem_color':showpercentage(item.percentage)}"></div>
                  </a-card>
                  </a-col>
              </div>
              </a-row>
              <br/><br/>
              <p class="resume_abilitysubtitle">Languages</p>
              <a-row :gutter="[25,25]">
                  <div v-for="(item, key) in languages" :key="key">
                      <a-col :span="12">
                      <a-card :title="item.langname" :bordered="false" class="resume_skilltitle">
                      <div slot="extra" class="resume_skillitemtitle">{{item.percentage}}%</div>
                      <div class="resume_skillitem" :style="{'--resume_skillitem_width': item.percentage, '--resume_skillitem_color':showpercentage(item.percentage)}"></div>
                      </a-card>
                      </a-col>
                  </div>
              </a-row>
              <br/><br/>
              <p class="resume_buildtools">This project is build using Vue.js framework</p>
              <button class="resume_projects_btn" @click="handleToProjectPage()">Projects in Github</button>
          </div>
       </div>
  </div>
</template>

<script>
export default {
  name: 'Resume',
  components: { 
    
  },
  data: () => ({
    resumetext1: "Hi, this is Andy, I am an Chinese web developer, currently in Australia. I really love interesting coding and making friends",
    resumetext2: "If we meet in one day future, I will treat you as good friend and have a tea together, and share our stories, DO YOU LIKE IT?",
    skills: [
      { skillname: 'JavaScript', percentage: 50 },
      { skillname: 'React.js', percentage: 60 },
      { skillname: 'Vue.js', percentage: 20},
      { skillname: 'Express.js', percentage: 30},
      { skillname: 'Node.js', percentage: 40 },
      { skillname: 'C#', percentage: 30},
      { skillname: 'SQL', percentage: 50},
      { skillname: 'Unity', percentage: 50},
      { skillname: 'C++', percentage: 30},
      { skillname: 'Java', percentage: 60},
      { skillname: 'HTML', percentage: 30},
      { skillname: 'CSS', percentage: 60},
      { skillname: 'Android Studio', percentage: 40},
      { skillname: 'Firebase', percentage: 40},
    ],
    languages: [
      {langname: "Chinese", percentage: 100},
      {langname: "English", percentage: 70}
    ]
  }),
  methods:{
    showpercentage(e){
      if(e<=30){return "rgb(143, 6, 6)";}
      else if (e>30 && e<=50){return "rgb(141, 141, 2)";}
      else if (e>50){return "rgb(3, 94, 3)"}
    },
    handleToProjectPage(){window.open("https://github.com/Yunwei-Zhang", '_blank');}
  }
}
</script>

<style scoped src="@/views/resumepage/Resume.css">

</style>