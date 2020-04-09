<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <About v-if="about"/>
      <Projects
        v-if="projects"
        :viewProjectDetails="showProjectDetails"
        :project="featuredProject"
        :softwareProjects="softwareProjects"
        :designProjects="designProjects"
        :videoProjects="videoProjects"
      />
      <ProjectDetails
        data-aos="fade-in"
        v-if="projectDetails"
        :project="featuredProject"
        @viewProjectDetails="showProjectDetails"
      />
      <Contact v-if="contact"/>
    </div> 
  </div>
</template>

<script>
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import ProjectDetails from './components/ProjectDetails.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    About,
    Projects,
    ProjectDetails,
    Contact,
  },
  data() {
    return {
      currentPg: '',
      about: true,
      projects: false,
      contact: false,
      projectDetails: false,
      featuredProject: {},
      softwareProjects: [
        {
          id: 1,
          title: 'Kwik-e-Mart',
          description: 'Full stack mock e-commerce website',
          details: 'Welcome to Kwik-e-Mart, a full stack CRUD application with RESTful API architecture. Users can filter and select groceries for their shopping cart, add a payment method, and edit / confirm their order before checkout.',
          stack: ['Vue', 'Vue Router', 'Node', 'Express', 'Axios', 'Sequelize', 'PostgreSQL'],
          github: [
            {
              link: 'https://github.com/matt-violet/Kwik-E-Mart-frontend',
              repo: 'GitHub Repository - Front End'
            },
            {
              link: 'https://github.com/matt-violet/Kwik-E-Mart-backend',
              repo: 'GitHub Repository - Back End'
            }  
          ],
          image: require('./images/kwik-e-mart.png'),
          video: 'https://www.youtube.com/embed/CLBsz0dTiEk'
        },
        {
          id: 2,
          title: 'Segment Events',
          description: 'Harnessing the power of user event data',
          details: 'As an intern at Seasoned I integrated Segment events (from Segment\'s Customer Data Platform) to collect data about admin onboarding events. This information is now used by the Data and Marketing teams to drive analytics, A/B testing, and automated marketing campaigns.',
          stack: ['Javavscript', 'React', 'Segment Library'],
          github: '',
          image: require('./images/segment.png'),
          video:require('./images/segment.png')
        },
        {
          id: 3,
          title: 'Internal Tool',
          description: 'Components for customer service tool',
          details: 'As an intern at Seasoned I developed reusable components for an internal tool for the Customer Service team. In addition to building stylized menus and cards for admins, job seekers, and stores, I implemented GraphQL queries to fetch relevant data from a Postgres database.',
          stack: ['Javavscript', 'Vue', 'Vuetify', 'GraphQL', 'PostgreSQL'],
          github: '',
          image: require('./images/vuetify.png'),
          video:require('./images/vuetify.png')
        },
        {
          id: 4,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          details: 'Built responsive image gallery with modal view showing photo details, flagging options, and intuitive navigation. Designed database schema to optimize loading speeds by hosting images in AWS S3 buckets.',
          stack: ['HTML', 'CSS (grid, media query)', 'Javascript', 'React', 'Styled-Components', 'Express', 'MongoDB', 'Faker', 'Jest', 'Enzyme'],
          github: 'https://github.com/krummurk/photos-module',
          image: require('./images/restaurant.jpg'),
          video: 'https://www.youtube.com/embed/LZBo0UIRxvI'
        },
        {
          id: 5,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
          details: 'Scaled the back end of a room reviews app to handle 10 million records and 100 requests per second. Benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. Deployed app on AWS and stress tested server to identify performance bottlenecks.',
          stack: ['PostgreSQL', 'Cassandra', 'Express', 'Amazon Web Services', 'k6', 'New Relic'],
          github: 'https://github.com/social-inn/Reviews',
          image: require('./images/bed.jpg'),
          video: require('./images/social-in-test.png')
        },
        {
          id: 6,
          title: 'Connect Four',
          description: 'Single Page Connect Four Game',
          details: 'Developed game in which two players alternately place pieces into a 7x7 board trying to place 4 adjacent pieces. Implemented animations and dynamically rendering board, game status, and rematch button.',
          stack: ['HTML', 'CSS', 'Javascript', 'React'],
          github: 'https://github.com/matt-violet/connect4',
          image: require('./images/connect-four.png'),
          video: 'https://www.youtube.com/embed/AM0sI6ZqEQw'
        },
        {
          id: 7,
          title: 'My Bolus',
          description: 'Insulin dose calculator for diabetics',
          details: 'Developed an app to simulate modern insulin pump dosage algorithms based on user’s meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors. Below is a theoretical example of the kind of mental calculations insulin users must perform ahead of every meal.',
          stack: ['HTML', 'CSS', 'Javascript', 'React', 'Express', 'MongoDB'],
          github: 'https://github.com/matt-violet/My-Bolus',
          image: require('./images/vial.jpg'),
          image2: require('./images/bolus-math.png'),
          ppt: 'https://drive.google.com/file/d/1D8tp35PoCCbMzuWLTPHFI5oGN7nFhIQ1/view?usp=sharing',
          video: 'https://www.youtube.com/embed/OsGm4uK7SEs'
        }
      ],
      designProjects: [
        {
          image: require('./images/Symposium2019.jpg'),
          description: 'Event Flyer, 2019',
          design: true
        },
        {
          image: require('./images/GA2017.png'),
          description: 'Recruitment Flyer, 2018',
          design: true
        },
        {
          image: require('./images/SKSM-banner.jpg'),
          description: '8-foot Retractable Banner, 2017',
          design: true
        },
        {
          image: require('./images/GA2016-flyer.png'),
          description: 'Ad in UU World Magazine, 2016',
          design: true
        },
        // {
        //   image: require('./images/GA2017-flyer.png'),
        //   description: 'Ad in UU World Magazine, 2017',
        //   design: true
        // },
        {
          image: require('./images/GA2018-flyer.png'),
          description: 'Ad in UU World Magazine, 2018',
          design: true
        },
        {
          image: require('./images/HLTW.png'),
          description: 'Designed page layouts for the book "Hunter Leads the Way", 2017',
          design: true
        },
        {
          image: require('./images/SEAsia.png'),
          description: 'Graphic for Personal Project, 2015',
          design: true
        },
        {
          image: require('./images/matt-oak.png'),
          description: 'Graphic for Personal Project, 2019',
          design: true
        },
      ],
      videoProjects: [
        {
          title: 'Starr King Threshold Ceremony, 2017',
          description: 'The Starr King community gathers to welcome new students to the school.',
          url: 'https://www.youtube.com/embed/Boi3G8wiEAY'
        },
        {
          title: 'A Mindful Walk, 2018',
          description: 'Experience Transylvania\'s hills and river valleys, cultural sites, and more in this unforgettable immersion couse.',
          url: 'https://www.youtube.com/embed/6eKqxxVSlKQ'
        },
        {
          title: 'Soaring Sunday, 2015',
          description: 'Discover the art of soaring as we take flight over Byron, CA in this meditative weekend recap.',
          url: "https://player.vimeo.com/video/118749275"
        }
      ],
    }
  },
  methods: {
    onMenuClick(option) {
      this.home = false;
      this.about = false;
      this.projects = false;
      this.contact = false;
      this[option] = true;
      this.currentPg = option;
    },
    showProjectDetails(project) {
      this.featuredProject = project;
      this.projectDetails = !this.projectDetails;
    },
  }
}
</script>

<style>
  body, html {
    min-height: 100%;
    min-width: 600px;
    margin: 0;
    font-family: 'IBM Plex Sans', 'Montserrat', sans-serif;
  }
  a {
    color: blue;
    font-weight: 400;
  }
</style>
