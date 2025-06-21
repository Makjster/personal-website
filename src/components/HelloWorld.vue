<template>
  <div>
    <div class="container content">
      <div class="row py-5">
        <!-- Navigation Section -->
        <div class="col-lg-4">
          <div class="nav-container">
            <div id="about">
              <div>
                <h1 class="text-2xl font-bold leading-tight lg:text-4xl lg:leading-none text-zenith" style="color: #fff;">Matti Johannsen</h1>
                <h2 class="mt-16 text-[22px] font-semibold leading-tight text-sunrise" style="color: #fff;">Software Developer & IT Consultant</h2>
              </div>
              <div class="row">
                <div class="col-md-9">
                  <p>
                    I am a dynamic and dedicated software developer with a zealous commitment to learning and staying abreast of the latest technological advancements. My professional journey in the realm of software development commenced in 2021, post-acquisition of my Bachelor's degree in Computer Science from the RWTH Aachen University.
                  </p>
                </div>
              </div>
            </div>
            <nav class="navigation">
              <ul>
                <li v-for="(section, index) in sections" :key="index">
                  <a :href="'#' + section.id" :class="{ active: section.isActive }">{{ section.label }}</a>
                </li>
              </ul>
            </nav>
            <div class="contact-links">
              <a href="https://www.linkedin.com/in/matti-johannsen-9950871b3/" target="_blank"><i class="fab fa-linkedin"></i> LinkedIn</a> |
              <a href="https://github.com/Makjster" target="_blank"><i class="fab fa-github"></i> GitHub</a> |
              <a href="mailto:Matti.Johannsen@gmx.de"><i class="fas fa-envelope"></i> Email</a>
            </div>
          </div>
        </div>

        <!-- Main Content Section -->
        <div class="col-lg-8">
          <div id="experience" class="section-container">
            <h2>Experience</h2>
            <div class="experience-container">
              <div v-for="(experience, index) in experienceItems" :key="index" class="experience-item" @click="openLink(experience.url)" style="cursor:pointer">
                <div class="row">
                  <div class="col-md-3">
                    <h3>{{ experience.date }}</h3>
                  </div>
                  <div class="col-md-9">
                    <h3>{{ experience.role }}</h3>
                    <h4>{{ experience.company }}</h4>
                    <ul>
                      <li v-for="(item, itemIndex) in experience.details" :key="itemIndex">{{ item }}</li>
                    </ul>
                  </div>
                  <div class="col-md-3">
                    <h3>Skills</h3>
                  </div>
                  <div class="col-md-9">
                    {{ experience.skills }}
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div id="academic" class="section-container">
            <h2>Academic Background</h2>
            <div class="academic-container">
              <div v-for="(academic, index) in academicItems" :key="index" class="academic-item" @click="openLink(academic.url)" style="cursor:pointer">
                <div class="row">
                  <div class="col-md-3">
                    <h3>{{ academic.date }}</h3>
                  </div>
                  <div class="col-md-9">
                    <h3>{{ academic.degree }}</h3>
                    <h4>{{ academic.institution }}</h4>
                    <ul>
                      <li v-for="(item, itemIndex) in academic.details" :key="itemIndex">{{ item }}</li>
                    </ul>
                  </div>
                  <div class="col-md-3">
                    <h3>Skills</h3>
                  </div>
                  <div class="col-md-9">
                    {{ academic.skills }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer text-center py-3"><a href="impressum.html">Impressum</a></div>
  </div>
</template>

<script>
import '@/assets/css/main.css'; // Import the CSS file

export default {
  data() {
    return {
      sections: [
        { id: 'experience', label: 'Experience', isActive: false },
        { id: 'academic', label: 'Academic Background', isActive: false },
      ],

      experienceItems: [
        {
          date: '2025-today',
          role: 'Senior Solutions Architect',
          company: 'ZiScom Solutions GmbH',
          details: [
            'Design and implementation of software solutions for electronic invoice processing.',
            'Engineering scalable and resilient enterprise content management platforms, leveraging Java to design tailored solutions that meet complex business needs.',
            'Planning and implementation of large-scale document and metadata migrations, ensuring integrity, traceability, and minimal downtime.',
          ],
          skills: 'Java, Git, AWS, Spring, Linux, Maven',
          url: 'https://ziscom.solutions/'
        },
        {
          date: '2023-2024',
          role: 'IT Consultant',
          company: 'SER Group',
          details: [
            'Development and customization of highly complex and highly available ECM systems and, in particular, with a focus on Java development',
            'Leading a working group focused on cloud technologies in the Community of Practice "Cloud"',
            'Architecture of software implementation projects in the cloud (S2S VPN) as well as on-premise',
            'Consultation on all phases of the software implementation process, from solution design to completion of the hyper-care phase',
          ],
          skills: 'Java, Groovy, Git, AWS, Spring, Linux, Maven',
          url: 'https://www.sergroup.com/en/'
        },
        {
          date: '2021-2023',
          role: 'Junior Consultant',
          company: 'Seven Principles Group',
          details: [
            'Developed an innovative, cloud-based platform for streamlined freelance management',
            'Created an efficient and user-friendly solution',
            'Performed database migrations in AWS',
          ],
          skills: 'Java, Git, AWS, Spring, Linux, Gradle',
          url: 'https://7p-solutions-consulting.com/en/'
        },
      ],
      academicItems: [
        {
          date: '2017-2021',
          degree: "Bachelor's Degree",
          institution: 'RWTH Aachen',
          details: [
            'Obtained a Bachelor\'s degree in Computer Science',
            'Minor in Economics',
          ],
          skills: '',
          url: 'https://www.rwth-aachen.de/go/id/a/?lidx=1'
        },
        {
          date: '2018-2021',
          degree: 'Student Assistant',
          institution: 'Chair of Individualized Production in Architecture',
          details: [
            'Development of an MQTT-based software tool for precise robot control',
            'Conceptualized and implemented a Rust-based web application, establishing it as a benchmark',
            'Engineered a PHP-based authentication web service with a comprehensive user database',
            'Proficiency in adapting web design elements across multiple services',
            'Played a crucial role in software design for seamless data exchange between diverse systems',
            'Systems include Computer-Aided Design, Computer-Aided Manufacturing, and Building Information Modeling',
          ],
          skills: 'C#, WPF, Research, PHP, HTML, CSS, Hugo',
          url: 'https://www.ip.rwth-aachen.de/'
        },
        {
          date: '2020',
          degree: 'Tutoring Experience',
          institution: 'Chair of Communication and Distributed Systems',
          details: [
            'Tutor for the course Datacommunication and Security',
            'Assisted students with understanding complex concepts',
            'Facilitated discussions and provided guidance on practical assignments',
            'Honed communication and presentation skills',
          ],
          skills: '',
          url: 'https://www.comsys.rwth-aachen.de/home'
        },
        {
          date: '2021',
          degree: "Bachelor's Thesis",
          institution: 'Uniklinikum Aachen',
          details: [
            'Bachelor\'s thesis at the chair of Software Engineering in collaboration with the Uniklinikum Aachen',
            'Topic: Development of a Domain-Specific Language for Controlling a Syringe Pump of a Pharmaceutical Synthesis Plant',
            'Developed a DSL that can control a syringe pump via an interface',
          ],
          skills: 'C#, WPF, Java',
          url: 'https://www.ukaachen.de/en/'
        },
      ],
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeMount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
  const scrollPos = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
  this.sections.forEach(section => {
    const offsetTop = document.getElementById(section.id).offsetTop - 75; // Adjust the offset as needed
    const offsetBottom = offsetTop + document.getElementById(section.id).offsetHeight;
    section.isActive = scrollPos >= offsetTop && scrollPos < offsetBottom;
  });
},
    openLink(url) {
      window.open(url, '_blank');
    }
  },
};
</script>