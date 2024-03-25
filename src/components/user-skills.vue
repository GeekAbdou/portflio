<template>
  <div>
    <div class="skills__section skills__frontend">
      <h2 class="skills__heading">&lt;Frontend/&gt;</h2>
      <ul class="skills__list">
        <!-- Iterate over the frontend skills -->
        <li class="skills__item" v-for="skill in frontendSkills" :key="skill.name">
          <img :src="skill.icon" :alt="skill.name" class="skills__icon" />
        </li>
      </ul>
    </div>

    <div class="skills__section skills__backend">
      <h2 class="skills__heading">&lt;Backend/&gt;</h2>
      <ul class="skills__list">
        <!-- Iterate over the backend skills -->
        <li class="skills__item" v-for="skill in backendSkills" :key="skill.name">
          <img :src="skill.icon" :alt="skill.name" class="skills__icon" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      // Mock data, replace with actual paths and names
      frontendSkills: [
        { name: 'HTML5', icon: 'path-to-html-icon.png' }
        // ... other frontend skills
      ],
      backendSkills: [
        { name: 'Node.js', icon: 'path-to-node-icon.png' }
        // ... other backend skills
      ]
    }
  }
}
</script>

<style lang="scss">
.skills__section {
  margin: 20px;
  border: 1px solid #ccc;
  padding: 10px;
}

.skills__heading {
  font-size: 1.5em;
  margin-bottom: 15px;
  text-align: center;
}

.skills__list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.skills__item {
  width: 50px; // Adjust the size accordingly
  height: 50px;
  margin: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.skills__icon {
  max-width: 100%;
  max-height: 100%;
}
</style>
