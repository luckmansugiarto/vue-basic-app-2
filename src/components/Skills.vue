<template>
  <div>
    <div class="holder">
      <form @submit.prevent="addSkill()">
        <input type="text" placeholder="Enter a skill you have..." v-model="skill" v-validate="{ required: true, min: 5 }" name="skill"/>

        <transition name="alert-in" enter-active-class="animated flipInX" leave-active-class="animated flipOutX">
          <p class="alert" v-if="errors.has('skill')">
            {{ errors.first('skill') }}
          </p>
        </transition>
      </form>

      <transition-group tag="ul" name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data, index) in skills" :key="index">
          {{ index }}. {{ data.skill }}
          <a href="javascript:;" @click="deleteSkill(index)" class="animated">
            <i class="material-icons">delete</i>
          </a>
        </li>
      </transition-group>

      <p>These are the skills that you possess</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data () {
    return {
      name: 'PHP',
      skill: '',
      skills: [
        { 'skill': 'Vue.js' },
        { 'skill': 'Frontend Developer' }
      ]
    }
  },
  methods: {
    addSkill () {
      this.skills.push({ skill: this.skill })
      this.clearInput()
    },
    clearInput () {
      this.skill = ''
    },
    deleteSkill (index) {
      this.skills.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./Skills.css" scoped></style>
