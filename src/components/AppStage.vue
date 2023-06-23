<template>
  <div class="app-stage">
    <div class="color-morph top" />
    <header class="app">
      <JHMonogram class="jmh" />
      <nav class="top">
        <a 
          v-for="mode in modeOptions" 
          :href="`#${mode}`"
          :key="mode" 
          @click="updateMode(mode)"
          >{{ mode === 'designSystems' ? designSysLabel : mode }}</a>
      </nav>
    </header>
    <main>
      <section class="top-about shaper-ready">
        <Me class="me" />
        <div class="intro shaper-ready">
          <h2>Hi, I'm <strong>Jason</strong></h2>
          <span>I'm a Software Engineer && UI/UX/U∞ Designer from Austin, TX. I like to design it and I like to make it work beautifully. And for as many people as possible. Thanks for stopping by.</span>
        </div>

        <Shaper class="shaper-stage" />
      </section>

      <nav class="large-nav">
        <a 
          v-for="mode in modeOptions"
          :href="`#${mode}`"
          :key="mode" 
          :class="[mode === activeMode ? 'active' : '', mode ? mode : null]"
          @click="updateMode(mode)"
          >{{ mode === 'designSystems' ? designSysLabel : mode }}</a>
      </nav>

      <section class="panel prototyping">
        <a name="prototyping" />
        <div class="left-pane">
          <h2>Prototyping</h2>
          <p>{{ protoText }}</p>

          <section class="skills">
            <span v-for="skill in protoSkills" :key="skill">{{ skill }}</span>
          </section>
        </div>
        <div class="right-pane">
          <h3>Wireframes for Project at Dun & Bradstreet - 2019</h3>
          <h4>PROJECT: Master Data Analysis and Education Tool</h4>
          <section class="img-gallery">
            <img src="/prototyping/prototyping1.png" class="galleriable" alt="D&B | Master Data Analysis and Education Tool" />
            <img src="/prototyping/prototyping2.png" class="galleriable" alt="D&B | Master Data Analysis and Education Tool" />
            <img src="/prototyping/prototyping3.png" class="galleriable" alt="D&B | Master Data Analysis and Education Tool" />
            <img src="/prototyping/prototyping4.png" class="galleriable" alt="D&B | Master Data Analysis and Education Tool" />
          </section>

          <h3>Wireframes for Project at Okta - 2021</h3>
          <h4>PROJECT: Solution Engineer Portal</h4>
          <section class="img-gallery">
              <img src="/prototyping/udp1.png" class="galleriable" alt="Okta | Solution Engineer Sales Portal" />
              <img src="/prototyping/udp2.png" class="galleriable" alt="Okta | Solution Engineer Sales Portal" />
              <img src="/prototyping/udp3.png" class="galleriable" alt="Okta | Solution Engineer Sales Portal" />
              <img src="/prototyping/udp4.png" class="galleriable" alt="Okta | Solution Engineer Sales Portal" />
          </section>

          <section v-for="link in protoLinks" :key="link.name" class="functional-app img-gallery-alt">
            <h3>{{ link.name }}</h3>
            <h4>{{ link.subtitle }}</h4>

            <img :src="link.imgSrc" class="galleriable" :alt="`${link.name}`" />

            <a :href="link.href" target="_blank noreferrer" :style="{ backgroundImage: `url(${link.bgImg})` }"><span>Try It Yourself</span></a>

            <p>{{ link.about }}</p>
          </section>
        </div>
      </section>

      <section class="panel dashboards">
        <a name="dashboards" />
        <div class="left-pane">
          <h2>Dashboards/Data Viz</h2>
          <p>{{ dashText }}</p>

          <section class="skills">
            <span v-for="skill in dashSkills" :key="skill">{{ skill }}</span>
          </section>
        </div>
        <div class="right-pane">
          <section class="img-gallery-alt">
            <h3>Composable Dashboard at Q2 - 2019-2023</h3>
            <h4>Customizable Dashboards used by millions</h4>
            <img src="/dashboards/comp-dash-quick-glance.gif" class="galleriable" alt="Q2 | Composable Dashboard" />
            <p>This product is the combined effort of mamy teams across multiple verticals, but I was lucky enough to get to contribute heartily to the core display logic (combo of web components and custom markup) and styles (combo of grid and flex layouts). I helped guide this successful product from ideation to millions of users.</p>

            <h3>Data Optimizer at D&B - 2019</h3>
            <h4>Tell the story of data's journey from dirty to actionable</h4>
            <img src="/dashboards/optimizer.gif" class="galleriable" alt="D&B | Data Optimizer" />
            <p>I love the challenge of using the browser as a narrative vehicle. This app walks users through the lifecycle of data records; both clean and in need of maintenance. Modern CSS and SVGs make it possible to tell stories in compelling ways.</p>

            <h3>Advanced API Monitoring at D&B - 2019</h3>
            <h4>Monitoring millions of API interactions daily</h4>
            <img src="/dashboards/advanced-monitoring.png" class="galleriable" alt="D&B | API Monitoring Dashboard" />
            <p>Everyday, D&B tracks millions of companies all over the world on over 250 data points per company. Advanced Monitoring allows companies to wade through this data and build their own insights on their customers and competitors. </p>

            <h3>Family Tree Explorer at D&B - 2019</h3>
            <h4>Browse relationship trees within public companies</h4>
            <img src="/dashboards/family-tree-explorer.gif" class="galleriable" alt="D&B | Family Tree Explorer" />
            <p>The impetus for this app was "how can we represent the many entities witin a complex company visually?" Using D&B's massive dataset, we used opacity to give a sense of depth and spacial positioning.</p>

            <h3>Company Location Plotter at D&B - 2019</h3>
            <h4>Mapping the locations of public company entities</h4>
            <img src="/dashboards/ubo-map.gif" class="galleriable" alt="D&B | Company Location Plotter" />
            <p>Another app based on the question: "how can we represent the many entities witin a complex company visually?" This app plots company HQs on a map to help provide context through physical locations.</p>

            <h3>Data Maturity Matrix at D&B - 2018</h3>
            <h4>Visualizing the state of a customer's Master Data Management Program</h4>
            <img src="/dashboards/maturity-matrix.gif" class="galleriable" alt="D&B | Data Maturity Matrix" />
            <p>This app helps users diagnose their own Master Data Management Program efficiency and get feedback on performance and insight through a series of questions. A few different charts help users understand their MDM Program in greater detail.</p>
          </section>
        </div>
      </section>

      <section class="panel design-systems">
        <a name="designSystems" />
        <div class="left-pane">
          <h2>Design Systems</h2>
          <p>{{ designSysText }}</p>

          <section class="skills">
            <span v-for="skill in designSysSkills" :key="skill">{{ skill }}</span>
          </section>
        </div>
        <div class="right-pane">
          <section v-for="link in designSysLinks" :key="link.name" class="functional-app img-gallery-alt">
            <h3>{{ link.name }}</h3>
            <h4>{{ link.subtitle }}</h4>

            <img :src="link.imgSrc" class="galleriable" :alt="`${link.name}`" />

            <a :href="link.href" target="_blank noreferrer" :style="{ backgroundImage: `url(${link.bgImg})` }"><span>Try It Yourself</span></a>

            <p>{{ link.about }}</p>
          </section>
        </div>
      </section>

      <section class="bottom-shaper-wrapper">
        <div class="shaper-ready">
          <Shaper class="shaper-stage bottom" />
        </div>
      </section>

      <div class="grid-display bottom">
        <Grid />
      </div>
    </main>

    <section class="about-section">
      <a name="about" />

      <main>
        <div class="left-about">
          <h2>About Me</h2>

          <p>I've been working in software for over a decade, where Art & Science meet. Comfortable in web/software/application design and development, I am a Creative Technologist that loves to use browsers/UIs as a vehicle for user narratives. Forever interested in the person/machine interaction.</p>
            
          <p>I'm a Staff Software Engineer at Q2 where we strengthen communities by providing modern banking solutions for community and independent banks and credit unions. I write core features for millions of users across multiple teams and in multiple repos.</p>
          <p>Thanks so much for visiting. Cheers. - J(a)SON </p>
        </div>
        <div class="right-about">
          <h3>Find Me Out There</h3>
          <a href="https://www.drinkingtheink.com/" class="social" target="_blank">Personal Projects</a>
          <a href="https://www.linkedin.com/in/jasonmharrison/" class="social" target="_blank" >linkedin</a>
          <a href="https://github.com/drinkingtheink" class="social" target="_blank" >github</a>
          <a href="https://www.behance.net/drinkingtheink" class="social" target="_blank" >behance</a>
          <a href="https://dribbble.com/DrinkingtheInk" class="social" target="_blank" >dribbble</a>
          <a href="https://www.goodreads.com/user/show/124215009-jason-harrison" class="social" target="_blank" >goodreads</a>
        </div>
      </main>
    </section>

    <div class="grid-display top">
      <Grid />
    </div>

    <div class="color-morph bottom" />
  </div>

  <transition name="modal-fade">
    <Modal 
      v-if="openModal" 
      @close="openModal = false" 
      :imgSrc="activeImg.src" 
      :aboutText="activeImg.alt" 
      :imgColl="imgColl"
      :activeImgIndex="matchingLinkIndexInColl"
    />
  </transition>
</template>

<script>
import JHMonogram from './JHMonogram.vue';
import Me from './Me.vue';
import Grid from './Grid.vue';
import Shaper from './Shaper.vue';
import Modal from './Modal.vue';

// const colorSet = ['#54478c', '#2c699a', '#0db39e', '#83e377', '#f29e4c'];

export default {
  name: 'AppStage',
  components: {
    JHMonogram,
    Me,
    Grid,
    Shaper,
    Modal,
  },
  data() {
    return {
      openModal: false,
      activeMode: 'prototyping',
      modeOptions: [
        'prototyping',
        'dashboards',
        'designSystems',
        'about',
      ],
      protoText: 'Low-fidelity/clickable wireframes and functional POCs let us talk about possibilities...',
      protoSkills: [
        'Adobe Creative Suite', 'Figma', 'InVision', 'Lucidchart', 'Balsamiq', 'UX Research', 'Whiteboarding', 'Ideation', 'Vue.js', 'React', 'Ember.js',
      ],
      protoLinks: [
        {
          name: 'Swipe Library POC at Q2 - 2021',
          subtitle: 'Project: Finding the best library to use for a mobile experience',
          bgImg: '../../prototyping/swipe-poc.png',
          about: 'A simple, functional app was the best way to let stakeholders quickly review different functionality sets across several swiping library options. This allowed us to select what we determined to be the best option for the project and get started on real implementation.',
          href: 'https://swipe-poc.surge.sh/',
          imgSrc: '../../prototyping/swipe-poc-demo.gif',
        },
        {
          name: 'Configurable SVG Branding POC at Q2 - 2022',
          subtitle: 'Project: Iterating on the best end user experience',
          bgImg: 'https://www.drinkingtheink.com/banners/svg-brand-banner.png',
          about: 'We wanted to allow end users to brand their own in-app icons, but we weren\'t sure what controls to provide. So I threw together a few functional POCs that we could introduce in User Research to see which performed best.',
          href: 'https://icon-playground.netlify.app/',
          imgSrc: '../../prototyping/icon-playground-demo.gif',
        },
        {
          name: 'Background Gradient Tool at Q2 - 2020',
          subtitle: 'Project: Iterating on the best end user experience',
          bgImg: '../../prototyping/bg-gradient-demo.png',
          about: 'We wanted to allow end users to build their own hero banner areas where they could add their own images and colors. I threw together this POC app with some preliminary controls that helped us decide which facets to ultimately offer in the experience.',
          href: 'https://background-playground.netlify.app/',
          imgSrc: '../../prototyping/bg-gradient-demo.gif',
        },
      ],
      dashText: 'Helping the data tell the story or show the way...',
      dashSkills: [
        'JavaScript', 'TypeScript', 'Vue.js', 'React', 'Ember.js', 'DataViz', 'Chart.js', 'D3', 'Geoplotting', 'Animation', 'Accessibility', 'SVG', 'Laravel', 'Semantic Markup', 'Information Architecture',
      ],
      designSysText: 'Built-in consistent branding and functionality...',
      designSysSkills: [
        'Web Components', 'Stencil', 'Lit', 'Accessibility', 'Semantic Markup',
      ],
      designSysLinks: [
        {
          name: 'Carousel Element at Q2 - 2019-2023',
          subtitle: 'Accessible Carousel Element for the Tecton Design System',
          bgImg: '../../designSystems/tecton-bg.png',
          about: 'Can one build a truly accessible carousel? Probably not since by definition some content is hidden. But our customers demanded it and we gave it our best shot.',
          href: 'https://tecton.q2developer.com/ui/q2-carousel',
          imgSrc: '../../designSystems/q2-carousel-demo.gif',
        },
      ],
      featuresText: 'Delivering what users want and what customers ask for...',
      featuresSkills: [
        'JavaScript', 'TypeScript', 'CSS3', 'Vue.js', 'React', 'Node.js', 'Express', 'Ember.js', 'Animation', 'SVG', 'Laravel', 'Webpack', 'Vite', 'Semantic Markup', 'Accessibility',
      ],
      designSysLabel: 'Design Systems',
      activeImg: null,
      imgColl: [],
    }
  },
  computed: {
    matchingLinkIndexInColl() {
      let linkMatch = null;

      if (this.activeImg) {
        linkMatch = this.imgColl.findIndex((img) => img.src === this.activeImg.src);
      }

      return linkMatch;
    },
    endOfImgColl() {
      return this.matchingLinkIndexInColl === (this.imgCount - 1);
    },
    beginningOfImgColl() {
      return this.matchingLinkIndexInColl === 0;
    },
    imgCount() {
      return this.imgColl?.length ? this.imgColl.length : 0;
    },
  },
  mounted() {
    this.makeImgsClickable();

    document.addEventListener('keydown', (event) => {
        if (event.key === 'ArrowRight' && this.openModal && !this.endOfImgColl) {
          this.activeImg = this.imgColl[this.matchingLinkIndexInColl + 1];
        } else if (event.key === 'ArrowLeft' && this.openModal && !this.beginningOfImgColl) {
          this.activeImg = this.imgColl[this.matchingLinkIndexInColl - 1];
        }
    });
  },
  methods: {
    updateMode(mode) {
      this.activeMode = mode;
    },
    makeImgsClickable() {
      const galleryImg = document.querySelectorAll('.galleriable');

      galleryImg.forEach((img) => {
        img.addEventListener('click', () => {
          console.dir(img);
          this.activeImg = img;
          this.openModal = true;
          this.imgColl = [...img.parentElement.children].filter((img) => img.nodeName && img.nodeName === 'IMG');
        });
      });
    },
    showModal() {
      this.openModal = true;
    },
    closeModal() {
      this.openModal = false;
      this.activeImg = null;
      this.imgColl = [];
    },
  }
}
</script>

<style lang="scss">
$headerSize: 35px;
$sheerBg: rgba(0, 0, 0, 0.8);

$col1: #54478c;
$col2: #2c699a;
$col3: #0db39e;
$col4: #83e377;
$col5:#f29e4c;
$col6: #06365c;

$appWidth: 1200px;

$boxShadow: 0px 3px 5px 3px rgba(0,0,0,0.36);
$boxShadowDark: 0px 3px 10px 3px rgba(0,0,0,0.8);

body {
  background-color: $col2;
  background-image: url("data:image/svg+xml,%3Csvg width='100' height='20' viewBox='0 0 100 20' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M21.184 20c.357-.13.72-.264 1.088-.402l1.768-.661C33.64 15.347 39.647 14 50 14c10.271 0 15.362 1.222 24.629 4.928.955.383 1.869.74 2.75 1.072h6.225c-2.51-.73-5.139-1.691-8.233-2.928C65.888 13.278 60.562 12 50 12c-10.626 0-16.855 1.397-26.66 5.063l-1.767.662c-2.475.923-4.66 1.674-6.724 2.275h6.335zm0-20C13.258 2.892 8.077 4 0 4V2c5.744 0 9.951-.574 14.85-2h6.334zM77.38 0C85.239 2.966 90.502 4 100 4V2c-6.842 0-11.386-.542-16.396-2h-6.225zM0 14c8.44 0 13.718-1.21 22.272-4.402l1.768-.661C33.64 5.347 39.647 4 50 4c10.271 0 15.362 1.222 24.629 4.928C84.112 12.722 89.438 14 100 14v-2c-10.271 0-15.362-1.222-24.629-4.928C65.888 3.278 60.562 2 50 2 39.374 2 33.145 3.397 23.34 7.063l-1.767.662C13.223 10.84 8.163 12 0 12v2z' fill='%2306365c' fill-opacity='0.4' fill-rule='evenodd'/%3E%3C/svg%3E");
}

@keyframes gradient {
	0% {
		background-position: 0% 50%;
	}
	50% {
		background-position: 100% 50%;
	}
	100% {
		background-position: 0% 50%;
	}
}

@keyframes colorGrad {
  0% {
    border-color: $col1;
  }
  20% {
    border-color: $col2;
  }
  40% {
    border-color: $col3;
  }
  60% {
    border-color: $col4;
  }
  80% {
    border-color: $col5;
  }
}

@mixin lrgbtn {
  display: block;
  height: 5rem;
  background-size: cover;
  background-position: 20%;
  box-shadow: $boxShadow;
  width: 80%;
  border-radius: 10px;
  margin: 1rem auto;
  text-decoration: none;
  text-transform: uppercase;
  color: $sheerBg;
  font-size: 1.5rem;
  transition: all 0.2s;
  position: relative;
  transform: scale(0.95);

  &:hover {
    box-shadow: $boxShadowDark;
    background-position: 90% -55%;
    transform: scale(1);

    span {
      background-color: rgba(palegreen,0.7);;
    }
  }

  span {
    position: absolute;
    top: 25%;
    right: 0;
    left: 0;
    margin: auto;
    text-shadow: 3px 3px 20px #fff,
      -2px 1px 30px #fff;
    padding: 10px;
    display: inline-block;
    transition: all 0.2s;
    background-color: rgba(255,255,255,0.5);
  }
}

.lrgbtn {
  @include lrgbtn();
}

.app-stage {
  position: relative;

  .color-morph {
    // background: linear-gradient(-45deg, #22577a, #38a3a5, #57cc99, #80ed99, #c7f9cc);
    background: linear-gradient(-45deg, #54478c, #2c699a, #0db39e, #83e377, #f29e4c);
    background-size: 700% 700%;
    animation: gradient 15s ease infinite;
    height: 100vh;
    padding-bottom: 10rem;
    height: 1500px;
    width: 1500px;
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    text-align: center;

    &.top {
      top: -900px;
      transform: rotate(45deg);
    }

    &.bottom {
      top: 2000px;
      transform: rotate(200deg);
    }
  }
}

$btnColor: rgba(255,255,255,0.9);

header.app {
  padding-top: 10px;
  height: $headerSize;
  margin-bottom: 10px;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  justify-content: center;
  align-content: center;
  z-index: 10;
  position: sticky;
	top: 0;
  border-top: 2px solid $col3;
  animation: colorGrad;
  animation-iteration-count: infinite;
  animation-duration: 10s;
  animation-direction: alternate-reverse;

  a {
    border: none;
    background: $sheerBg;
    padding: 10px 20px;
    margin-right: 5px;
    color: $btnColor;
    transition: all .2s;
    border-radius: 10px;
    text-transform: uppercase;
    text-decoration: none;

    &:hover {
      color: palegreen;
      background: rgba(0, 0, 0, 1);
    }

    &.active {
      color: palegreen;
    }
  }
}

main {
  padding-bottom: 5rem;
  position: relative;
  z-index: 9;
  max-width: $appWidth;
  margin: 0 auto;
}

$textShad: 1px 2px 2px rgba(0,0,0,0.3);

.top-about {
  display: flex;
  justify-content: center;
  padding: 0 100px;
  margin: 2rem 0;

  .intro {
    max-width: 55%;
    text-align: left;
    font-size: calc(0.75rem + 0.75vw);
    line-height: 1.25;
    position: relative;
    z-index: 9;
    padding-bottom: 2rem;

    h2 {
      color: white;
      margin-top: 0;
    }

    h2, span {
      position: relative;
      z-index: 9;
      text-shadow: $textShad;
    }

    span {
      color: rgba(0,0,0,0.7);
    }
  }
}

nav.top {
  // padding-top: 10px;

  a {
    font-size: 70%;
    display: inline-block;
    margin-top: -4px;
  }
}

nav.large-nav {
  display: flex;
  justify-content: space-evenly;
  margin-bottom: 2rem;
  padding: 0 2rem;
  position: relative;
  z-index: 9;

  a {
    width: 24%;
    height: 200px;
    margin-right: 10px;
    border-radius: 10px;
    background: rgba(0,0,0,0.4);
    transition: all 0.2s;
    text-transform: uppercase;
    text-decoration: none;
    font-size: calc(0.75rem + 0.75vw);
    padding-top: 10px;
    transition: all 0.2s;
    color: rgba(255,255,255,0.8);

    &:hover {
      transform: translateY(-10px);
      color: palegreen;
    }
  }
}

.me {
  width: 25%;
  height: 25%;
  border: 3px solid white;
  border-radius: 50%;
  overflow: hidden;
  z-index: 10;
}

.intro {
  padding-left: 30px;
  margin-left: 20px;
}

.jmh {
  width: 30px;
  margin-top: -12px;
  margin-right: 10px;
}

.panel {
  margin: 0 2rem 2rem 2rem;
  padding: 1rem 1rem 3rem 1rem;
  background: rgba(255,255,255,1);
  border-radius: 10px;
  min-height: 20rem;
  box-shadow: $boxShadow;
  display: flex;
  position: relative;
  z-index: 9;

  .left-pane {
    padding: 0 2rem;
    width: 30%;
    font-size: calc(0.75rem + 1vw);
    position: relative;
    text-align: left;

    p {
      line-height: 1.25;
    }

    .skills {
      position: relative;

      span {
        display: inline-block;
        color: palegreen;
        padding: 10px 20px;
        margin: 5px 5px 0 0;
        background: rgba(0, 0, 0, 0.8);
        font-size: 50%;
        transition: all 0.2s;
        text-transform: uppercase;
        border-left: 4px solid palegreen;

        &:hover {
          background: rgba(0, 0, 0, 1);
          color: lightsalmon;
          border-color: lightsalmon;
        }
      }
    }

    .skills::before {
      content: 'SKILLS USED';
      display: block;
      border-top: 1px solid rgba(0,0,0,0.3);
      padding-top: 1rem;
      margin-top: 1rem;
      font-size: 80%;
    }
  }

  .right-pane {
    width: 70%;
    padding-left: 2rem;
    height: 37rem;
    overflow-y: scroll;

    h3 {
      padding-bottom: 0;
      margin-bottom: 0;
    }

    h4 {
      padding-top: 0;
      margin-top: 0;
      color: rgba(29, 13, 13, 0.6);
      text-transform: uppercase;
    }

    p {
      font-size: 1rem;
      line-height: 1.5;
      text-align: left;
      margin-bottom: 2rem;
      padding-right: 1rem;
    }

    .functional-app {
      display: block;

      a {
        @include lrgbtn;
      }
    }
  }

  .right-pane::-webkit-scrollbar {
    width: 15px;
  }

  .right-pane::-webkit-scrollbar-track {
    background: rgba(0, 0, 0, 0.3);
    border-radius: 10px;
  }

  .right-pane::-webkit-scrollbar-thumb {
    background-color: rgba(0, 0, 0, 0.8);
    border-radius: 10px;
  }
}

.grid-display {
  position: absolute;
  width: $appWidth;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  top: -0.5rem;
  z-index: 0;

  &.bottom {
    top: auto;
    bottom: 0;
    transform: rotate(180deg);
    z-index: -1;
    width: auto;
  }
}

.grid-bottom {
  bottom: 0;
}

.bottom-shaper-wrapper {
  height: 15rem;
}

@mixin imgGallery {
  transition: all 0.2s;
  border: 5px solid rgba(0, 0, 0, 0);

  &:hover {
    border-color: $sheerBg;
    cursor: pointer;
  }
}

.img-gallery {
  display: flex;
  flex-wrap: wrap;

  img {
    max-width: 45%;
    margin: 5px 5px 0 0;
    @include imgGallery;
  }
}

.img-gallery-alt {
  img {
    max-width: 95%;
    @include imgGallery;
  }
}

.about-section {
  background-color: $col6;
  position: relative;
  z-index: 9;
  color: white;
  text-align: left;
  font-size: 1.25rem;
  line-height: 1.5;
  transform: rotate(2deg);
  width: 110vw;
  border-bottom: 4px solid $col4;
  border-top: 6px solid white;
  box-shadow: $boxShadow;
  margin-top: -5rem;
  margin-left: -10px;

  .me.bottom {
    position: absolute;
    width: 14rem;
    height: 14rem;
    right: 78%;
    border: none;
    background: transparent;
  }

  main {
    max-width: $appWidth;
    display: flex;
    transform: rotate(-2deg);
    margin: 0 auto;

    h2 {
      text-shadow: $textShad;
      color: palegreen;
    }

    .right-about {
      width: 40%;
      padding-left: 2rem;

      a {
        display: block;
        text-transform: uppercase;
        color: rgba(0, 0, 0, 0.8);
        background-color: palegreen;
        transition: all 0.2s;
        text-decoration: none;
        margin-bottom: 5px;
        border-radius: 10px;
        padding: 5px 20px;
        width: 70%;

        &:hover {
          background-color: rgba(0, 0, 0, 0.8);
          color: palegreen;
        }
      }
    }

    .left-about {
      width: 60%;
      padding-right: 2rem;
    }
  }
}

button {
  border: none;
  border-radius: 5px;
  background-color: rgba(0, 0, 0, 0.8);
  color: $btnColor;
  padding: 5px 10px;
  text-transform: uppercase;
  transition: all 0.2s;

  &:hover {
    color: palegreen;
  }
}

// illustration animation
@keyframes dash {
  to {
    stroke-dashoffset: 0;
  }
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity .5s ease;
}
</style>
