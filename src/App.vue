<template>
  <div class="app-container">
    <nav class="navbar">
      <div class="nav-content">
        <h1>📚 Vue 3 Learning Exercises</h1>
        <ul class="nav-menu">
          <li 
            v-for="exercise in exercises" 
            :key="exercise.id"
            :class="{ active: currentExercise === exercise.id }"
          >
            <button @click="currentExercise = exercise.id">
              {{ exercise.title }}
            </button>
          </li>
        </ul>
      </div>
    </nav>

    <main class="main-content">
      <!-- Exercise 1: Hello World -->
      <Exercise1 v-if="currentExercise === 1" />
      
      <!-- Exercise 2: Counter -->
      <Exercise2 v-if="currentExercise === 2" />
      
      <!-- Exercise 3: Login Form -->
      <Exercise3 v-if="currentExercise === 3" />
      
      <!-- Exercise 4: Todo List -->
      <Exercise4 v-if="currentExercise === 4" />
      
      <!-- Exercise 5: Weather Dashboard -->
      <Exercise5 v-if="currentExercise === 5" />
      
      <!-- Exercise 6: Currency Converter -->
      <Exercise6 v-if="currentExercise === 6" />
      
      <!-- Exercise 7: Product Showcase -->
      <Exercise7 v-if="currentExercise === 7" />
      
      <!-- Exercise 8: Dashboard with Slots -->
      <Exercise8 v-if="currentExercise === 8" />
      
      <!-- Exercise 9: Photo Gallery -->
      <Exercise9 v-if="currentExercise === 9" />
      
      <!-- Exercise 10: GitHub User Finder -->
      <Exercise10 v-if="currentExercise === 10" />
      
      <!-- Exercise 11: Shopping Cart with Pinia -->
      <Exercise11 v-if="currentExercise === 11" />
      
      <!-- Exercise 12: Form with Composables -->
      <Exercise12 v-if="currentExercise === 12" />
    </main>
  </div>
</template>

<script>
import { ref } from 'vue'
import Exercise1 from './exercises/Exercise1.vue'
import Exercise2 from './exercises/Exercise2.vue'
import Exercise3 from './exercises/Exercise3.vue'
import Exercise4 from './exercises/Exercise4.vue'
import Exercise5 from './exercises/Exercise5.vue'
import Exercise6 from './exercises/Exercise6.vue'
import Exercise7 from './exercises/Exercise7.vue'
import Exercise8 from './exercises/Exercise8.vue'
import Exercise9 from './exercises/Exercise9.vue'
import Exercise10 from './exercises/Exercise10.vue'
import Exercise11 from './exercises/Exercise11.vue'
import Exercise12 from './exercises/Exercise12.vue'

export default {
  name: 'App',
  components: {
    Exercise1,
    Exercise2,
    Exercise3,
    Exercise4,
    Exercise5,
    Exercise6,
    Exercise7,
    Exercise8,
    Exercise9,
    Exercise10,
    Exercise11,
    Exercise12
  },
  setup() {
    const currentExercise = ref(1)
    
    const exercises = [
      { id: 1, title: '1. Hello World & Data Binding' },
      { id: 2, title: '2. Counter & Methods' },
      { id: 3, title: '3. Login Form & v-model' },
      { id: 4, title: '4. Todo List & v-for' },
      { id: 5, title: '5. Weather Dashboard' },
      { id: 6, title: '6. Currency Converter' },
      { id: 7, title: '7. Product Showcase' },
      { id: 8, title: '8. Dashboard with Slots' },
      { id: 9, title: '9. Photo Gallery' },
      { id: 10, title: '10. GitHub User Finder' },
      { id: 11, title: '11. Shopping Cart' },
      { id: 12, title: '12. Form with Composables' }
    ]

    return {
      currentExercise,
      exercises
    }
  }
}
</script>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: #f5f5f5;
}

.navbar {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 20px 0;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav-content {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 20px;
}

.navbar h1 {
  margin-bottom: 20px;
  font-size: 28px;
}

.nav-menu {
  display: flex;
  gap: 10px;
  list-style: none;
  flex-wrap: wrap;
}

.nav-menu li button {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border: 2px solid rgba(255, 255, 255, 0.3);
  padding: 8px 12px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 12px;
  transition: all 0.3s ease;
}

.nav-menu li button:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.nav-menu li.active button {
  background: white;
  color: #667eea;
  font-weight: bold;
  border-color: white;
}

.main-content {
  flex: 1;
  max-width: 1400px;
  margin: 0 auto;
  width: 100%;
  padding: 40px 20px;
}

@media (max-width: 768px) {
  .navbar h1 {
    font-size: 20px;
    margin-bottom: 15px;
  }

  .nav-menu {
    gap: 8px;
  }

  .nav-menu li button {
    padding: 6px 10px;
    font-size: 11px;
  }

  .main-content {
    padding: 20px 10px;
  }
}
</style>