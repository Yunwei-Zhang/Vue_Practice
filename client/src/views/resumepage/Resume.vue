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
              <p class="resume_abilitysubtitle">My Skills</p>
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
              <button class="resume_projects_btn" @click="handleToGithub()">Projects in Github</button>
          </div>

          <div class="resume_edu">
              <br/>
              <p class="resume_edutitle">Education</p>
                <a-timeline mode="alternate">
                      <a-timeline-item color="white" class="resume_edu_item">Dahushanlu primary school, Shanghai<br/><p class="resume_edu_item_time">2005.9 - 2010.6</p></a-timeline-item>
                      <a-timeline-item color="white" class="resume_edu_item">Kongjiangminban, Shanghai<br/><p class="resume_edu_item_time">2010.9 - 2014.6</p></a-timeline-item>
                      <a-timeline-item color="white" class="resume_edu_item">Yangpu high school, Shanghai<br/><p class="resume_edu_item_time">2014.9 - 2017.6</p></a-timeline-item>
                      <a-timeline-item color="white" class="resume_edu_item">University of Technology Sydney, Australia
                          <br/><p class="resume_edu_item_subtitle">Academic Degree:&nbsp;</p><p class="resume_edu_item_subcontent">Software Engineering</p>
                          <br/><p class="resume_edu_item_subtitle">GPA:&nbsp;</p><p class="resume_edu_item_subcontent">D</p>
                          <br/><p class="resume_edu_item_time">2019.2 - now</p>
                      </a-timeline-item>
                      <a-timeline-item color="white" class="resume_edu_item">Upcoming ...</a-timeline-item>
                </a-timeline>
          </div>

          <div class="resume_message">
              <div class="resume_message_left"><p class="resume_message_title">Send Me Message</p></div>
              <div class="resume_message_right">
                    From:&nbsp;&nbsp;&nbsp;<input v-model="message_email" class="resume_message_fromemail"/>
                    <br/>
                    To:&nbsp;&nbsp;&nbsp;<input value="zhangyunweiandy@163.com" readonly="readonly" class="resume_message_toemail"/>
                    <a-input type="textarea" v-model="message" class="resume_message_content"/>
                    <button class="resume_message_btn" @click="handleSendEmail()">Submit</button>
              </div>
          </div>
          
          <div class="resume_contact">
          
          </div>

          <div class="resume_copyright">
              <div class="resume_copyright_title"><a-icon type="check-circle" />&nbsp;Copyright 2021 - AndyZhang's Blog All rights reserved.</div>
              <div class="resume_copyright_subtitle">
                  <a-icon class="resume_copyright_icons" @click="handleToFacebook()" type="facebook" />&nbsp;
                  <a-icon class="resume_copyright_icons" @click="handleToIns()" type="instagram" />&nbsp;
                  <a-icon class="resume_copyright_icons" @click="handleToGithub()" type="github" />&nbsp;
                  <a-icon class="resume_copyright_icons" @click="handleToWechat()" type="wechat" />&nbsp;
                  <a-icon class="resume_copyright_icons" @click="handleToQQ()" type="qq" />&nbsp;
              </div>
          </div>
       </div>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';
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
      { skillname: 'Knime', percentage: 30},
      { skillname: 'Office', percentage: 50},
      { skillname: 'GitHub', percentage: 50},
    ],
    languages: [
      {langname: "Chinese", percentage: 100},
      {langname: "English", percentage: 70}
    ],
    message_email: 'Name',
    message: '',
  }),
  methods:{
    showpercentage(e){
      if(e<=30){return "rgb(143, 6, 6)";}
      else if (e>30 && e<=50){return "rgb(141, 141, 2)";}
      else if (e>50){return "rgb(3, 94, 3)"}
    },
    handleToFacebook(){window.open("https://www.facebook.com/yunwei.zhang.1610", '_blank');},
    handleToIns(){window.open("https://www.instagram.com/yunwei.zhang.1610/?hl=en", '_blank');},
    handleToGithub(){window.open("https://github.com/Yunwei-Zhang", '_blank');},
    handleToWechat(){alert("AndyZhangyunwei")},
    handleToQQ(){alert("2946139865")},
    handleSendEmail(){
      var emaildata = {
        from_name: this.message_email,
        to_name: "Andy Zhang",
        message: this.message,
      };
      emailjs.send('service_4vsf6p8', 'template_q4kocpc', emaildata, 'user_EaYLgVFJJmzyTnRXzMqvp')
        .then((result) => {
            console.log('SUCCESS!', result.text);
        }, (error) => {
            console.log('FAILED...', error.text);
        });
    },
  }
}
</script>

<style scoped src="@/views/resumepage/Resume.css">

</style>