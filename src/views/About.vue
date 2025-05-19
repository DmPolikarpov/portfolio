<script setup>

    const data = {
        description: [`I am JavaScript developer with experience in TypeScript, vanilla JS, Vue and modern web technologies, 
                        holding engineering degree and studied in Moscow Technological University 'STANKIN' and Middlesex University Dubai.
                        With 3.5 years of team experience, I specialize in HTML5, CSS3, JavaScript (ES6, DOM, BOM, AJAX), TypeScript,
                        webpack, Express, websockets, Python, Flask, Django, SQL, MySQL, SQLite, Postgres, adaptive and cross-browser, layouts, APIs, Flex, 
                        Grid, Sass, GitHub, Git, Photoshop, Figma, Canvas, Polymer and Vue.js (Options API, Composition API, Vue Router, Vuex, 
                        Vite, Vue CLI). I design highloaded services and optimize algoritms to improve user experience, understand SEO 
                        and REST API, and convert designs from Figma or Photoshop into code. Committed to creating beautiful, responsive, 
                        and user-friendly web applications.`,
                        `Currently I work as a JavaScript developer for Group of Companies “Triumph” (BlendForWeb team). We create a CAD system 
                        for clothes designers and I am responsible for 2D module of the application (front and backend) and module of 3d fitting room (frontend). 
                        Before that I was successfully doing the BSc Honours Information Technology program in Middlesex University Dubai 
                        (not completed for family reasons) and that fact in addition with my previous degree and engineering work experience allows me 
                        to complete the most difficult tasks using JavaScript, TypeScript and modern frontend frameworks. In addition to that 
                        I had an experience to create programs using Python, Java and C.`,
                        `Besides, I have a huge experience working as a manufacturing engineer, therefore I believe that my knowledge and skills would be useful
                        to ones that set ambitious goals.`
                    ]
    }
</script>

<template>
    <div class="container">
        <div class="section-title">About me</div>
        <div class="section-content">
            <p 
                v-for="(item, index) in data.description"
                :key="index"
            >{{ item }}</p>
        </div>
    </div>
</template>

<style scoped>
    .container {
        color: var(--text-color);
        font-size: var(--font-size);
        width: 80vw;
        max-width: 1200px;
        height: 70%;

        .section-title {
            text-align: center;
            font-size: var(--title-font-size);
            color: var(--active-color);
        }

    }

    .section-content {
        line-height: 1.8;
        letter-spacing: 0.2px;
        padding: 1.5rem;
        border-radius: 12px;
        
        p {
            color: var(--text-color);
            margin: 0;
            font-weight: 400;
            max-width: 100%;
            word-spacing: 0.5px;
            text-indent: 2em;
            text-align: justify;
        }
    }
</style>