<template>
  <h1>Nacho</h1>
  <!-- <CounterComp /> -->
  <button @click="_removeLastProject">Remove last project</button>

  <div v-show="pokemonType.type === 'Water'" v-for="pokemonType in pokemons" :key="pokemonType.id">
    <h1>{{ pokemonType.type }}</h1>
    <ProjectCard
      v-for="pokemon in pokemonType.data"
      :key="pokemon.id"
      :myTitle="pokemon.name"
      :buttonConfig="{ showButton: false }"
    >
      <template v-slot:subtitle>
        <h2>Hi!</h2>
      </template>
    </ProjectCard>
  </div>
  <AwesomeForm />
</template>

<script>
// import CounterComp from './components/CounterComp.vue';
import ProjectCard from './components/ProjectCard.vue'
import AwesomeForm from './components/AwesomeForm/AwesomeForm.vue'

export default {
  name: 'App',
  data() {
    return {
      projects: [
        {
          uuid: '4',
          name: 'Lorem ipsum',
          description: 'Lorem ipsum',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true',
          completed_on: 'June 10, 2021',
          subprojects: [
            {
              uuid: '4',
              name: 'Lorem ipsum',
              description: 'Lorem ipsum',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '3',
              name: 'Vectorify',
              description: 'User Experience Design',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '2',
              name: 'Dashcoin',
              description: 'Web Development',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '1',
              name: 'Simplify',
              description: 'UI Design & App Development',
              content:
                'Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true',
              completed_on: 'June 22, 2021'
            }
          ]
        },
        {
          uuid: '3',
          name: 'Vectorify',
          description: 'User Experience Design',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true',
          completed_on: 'June 10, 2021',
          subprojects: [
            {
              uuid: '4',
              name: 'Lorem ipsum',
              description: 'Lorem ipsum',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '3',
              name: 'Vectorify',
              description: 'User Experience Design',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '2',
              name: 'Dashcoin',
              description: 'Web Development',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '1',
              name: 'Simplify',
              description: 'UI Design & App Development',
              content:
                'Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true',
              completed_on: 'June 22, 2021'
            }
          ]
        },
        {
          uuid: '2',
          name: 'Dashcoin',
          description: 'Web Development',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true',
          completed_on: 'June 10, 2021',
          subprojects: [
            {
              uuid: '4',
              name: 'Lorem ipsum',
              description: 'Lorem ipsum',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '3',
              name: 'Vectorify',
              description: 'User Experience Design',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '2',
              name: 'Dashcoin',
              description: 'Web Development',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '1',
              name: 'Simplify',
              description: 'UI Design & App Development',
              content:
                'Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true',
              completed_on: 'June 22, 2021'
            }
          ]
        },
        {
          uuid: '1',
          name: 'Simplify',
          description: 'UI Design & App Development',
          content:
            'Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.',
          image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true',
          completed_on: 'June 22, 2021',
          subprojects: [
            {
              uuid: '4',
              name: 'Lorem ipsum',
              description: 'Lorem ipsum',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '3',
              name: 'Vectorify',
              description: 'User Experience Design',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '2',
              name: 'Dashcoin',
              description: 'Web Development',
              content:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true',
              completed_on: 'June 10, 2021'
            },
            {
              uuid: '1',
              name: 'Simplify',
              description: 'UI Design & App Development',
              content:
                'Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.',
              image: 'https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true',
              completed_on: 'June 22, 2021'
            }
          ]
        }
      ],
      pokemons: [
        {
          type: 'Water',
          id: 0,
          data: [
            {
              id: 0,
              name: 'Squirtle'
            },
            {
              id: 1,
              name: 'Wartoltle'
            },
            {
              id: 2,
              name: 'Blastoise'
            }
          ]
        },
        {
          type: 'Fire',
          id: 1,
          data: [
            {
              id: 0,
              name: 'Charmander'
            },
            {
              id: 1,
              name: 'Charmeleon'
            },
            {
              id: 2,
              name: 'Charizard'
            }
          ]
        },
        {
          type: 'Leaf',
          id: 2,
          data: [
            {
              id: 0,
              name: 'Bulbasaur'
            },
            {
              id: 1,
              name: 'Ivysur'
            },
            {
              id: 2,
              name: 'Venusur'
            }
          ]
        }
      ]
    }
  },
  components: {
    // CounterComp,
    ProjectCard,
    AwesomeForm
  },
  methods: {
    _removeLastProject() {
      this.projects.pop()
    },
    async _getProjectsData() {
      const data = await fetch(
        'https://raw.githubusercontent.com/ironhack-jc/mid-term-api/main/projects'
      )
      const response = await data.json()
      this.projects = response.filter((project) => project.name !== 'Lorem ipsum')
      console.log(this.projects)
    }
  },
  created() {
    console.log('APP --> Created')
    // this._getProjectsData()
  },
  mounted() {
    console.log('APP --> Mounted')
  }
}
</script>

<style scope>
.form--container {
  margin: 10px;
}
</style>
