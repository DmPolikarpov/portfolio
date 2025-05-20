<script setup>

    import jsIcon from "../assets/skill-icons/javascript.svg"
    import vue from "../assets/skill-icons/vue.svg"
    import npm from "../assets/skill-icons/npm.svg"
    import node from "../assets/skill-icons/node.svg"
    import htmlIcon from "../assets/skill-icons/html.svg"
    import sass from "../assets/skill-icons/sass.svg"
    import wpIcon from "../assets/skill-icons/webpack.svg"
    import exprIcon from "../assets/skill-icons/express.svg"
    import apiIcon from "../assets/skill-icons/api.svg"
    import ajaxIcon from "../assets/skill-icons/ajax.svg"
    import ghIcon from "../assets/skill-icons/github.svg"
    import pyIcon from "../assets/skill-icons/python.svg"
    import flask from "../assets/skill-icons/flask.svg"
    import django from "../assets/skill-icons/django.svg"
    import screenIcon from "../assets/skill-icons/screen.svg"
    import wbsockets from "../assets/skill-icons/websockets.svg"
    import tsIcon from "../assets/skill-icons/typescript.svg"
    import glIcon from "../assets/skill-icons/gitlab.svg"
    import sqlIcon from "../assets/skill-icons/sql.svg"
    import plmIcon from "../assets/skill-icons/polymer.svg"

    const skills = [
        { name: "HTML & CSS (Flex,Grid, Animation)", icon: htmlIcon },
        { name: "Sass", icon: sass },
        { name: "Responsive Design (All Screen Sizes)", icon: screenIcon },
        { name: "JavaScript", icon: jsIcon },
        { name: "TypeScript", icon: tsIcon },
        { name: "API & JSON", icon: apiIcon },
        { name: "Vue.js (Vue Router, Vuex, Vite, Vue CLI)", icon: vue },
        { name: "GitHub & Git", icon: ghIcon },
        { name: "GitLab", icon: glIcon },
        { name: "NPM", icon: npm },
        { name: "Node", icon: node },
        { name: "AJAX", icon: ajaxIcon },
        { name: "webpack", icon: wpIcon },
        { name: "Express", icon: exprIcon },
        { name: "websockets", icon: wbsockets },
        { name: "Python", icon: pyIcon },
        { name: "Flask", icon: flask },
        { name: "Django", icon: django },
        { name: "SQL (MySQL, SQLite, Postgres)", icon: sqlIcon },
        { name: "Polymer", icon: plmIcon }


    ];
</script>

<template>
  <div class="container">
    <div class="section-title">Skills</div>
    <div class="section-content">
      <div v-for="(item, index) in skills" :key="index" class="item-card">
        <div class="item-icon">
            <img :src="item.icon" class="logo" :alt="item.name" />
        </div>
        <div class="item-name">{{ item.name }}</div>
      </div>
    </div>
</div>
</template>

<style lang="scss" scoped>

.container {
    color: var(--text-color);
    font-size: 1em;
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
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 1.5rem;
  padding: 15px 1rem;
  justify-content: center;
  max-height: 100%;
  overflow-y: auto;
}

.item-card {
    background: #4e598e;
    padding: 0.5rem;
    border-radius: 12px;
    text-align: center;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 1px solid rgba(52, 152, 219, 0.2); // Subtle border
    &:hover {
        transform: translateY(-5px);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
    }
}

.item-icon {
    width: 40%;
    margin: 0 auto;
}

.item-name {

  color: #ccd3db;
  margin: 5px;
  font-weight: 500;
}

@media (max-width: 768px) {

  .section-title {
    font-size: 2em;
  }

  .section-content {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
  }

  .item-card {
    padding: 1rem;
  }

  .item-icon {

  }

}

@media (max-width: 480px) {

  .item-card {
    padding: 0.8rem;
  }

  .item-icon {
    font-size: 1.5em;
  }
}
</style>