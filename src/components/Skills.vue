<template>
  <div>
    <h1 class="display-4 mt-5">{{ title }}</h1>
    <!-- <form @submit.prevent="addSkill"> -->
    <div>
      <input type="text" placeholder="Add your skills" v-model="skill" class="mb-5 w-75">
      <button type="submit" @click="addSkill" :disabled="skill.length === 0">add</button>
    </div>
    <!-- </form> -->
    <div class="col-md-4">
      <ul v-for="(skillz, i) in skills" :key="skillz.skill" class="list-group">
        <li class="list-group-item">
          {{ skillz.skill }}
          <span @click="remove(i)" class="float-right">
            <i class="fas fa-trash red"></i>
          </span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Add your skills",
      skill: "",
      skills: []
    };
  },
  methods: {
    addSkill() {
      this.skills.push({ skill: this.skill });
      this.skill = "";
    },
    remove(id) {
      this.skills.splice(id, 1);
    }
  }
};
</script>

<style scoped>
.red {
  color: red;
  cursor: pointer;
}

input:focus {
  outline: none;
}
</style>
