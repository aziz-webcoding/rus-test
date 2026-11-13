<script setup>
import { ref } from 'vue'

const currentView = ref('quiz')

const itemsDatabase = [
  // --- МУЖСКОЙ РОД (0) ---
  {
    base: "карандаш", gender: 0, enNoun: "pencil", nounHint: "pencil - карандаш",
    colors: {
      red: { en: "Red pencil", ruAdj: "Красный", hint: "red - красный" },
      black: { en: "Black pencil", ruAdj: "Чёрный", hint: "black - чёрный" },
      blue: { en: "Blue pencil", ruAdj: "Синий", hint: "blue - синий" },
      green: { en: "Green pencil", ruAdj: "Зелёный", hint: "green - зелёный" },
      yellow: { en: "Yellow pencil", ruAdj: "Жёлтый", hint: "yellow - жёлтый" },
      big: { en: "Big pencil", ruAdj: "Большой", hint: "big - большой" },
      small: { en: "Small pencil", ruAdj: "Маленький", hint: "small - маленький" }
    }
  },
  {
    base: "стол", gender: 0, enNoun: "table", nounHint: "table - стол",
    colors: {
      red: { en: "Red table", ruAdj: "Красный", hint: "red - красный" },
      black: { en: "Black table", ruAdj: "Чёрный", hint: "black - чёрный" },
      big: { en: "Big table", ruAdj: "Большой", hint: "big - большой" },
      green: { en: "Green table", ruAdj: "Зелёный", hint: "green - зелёный" }
    }
  },
  {
    base: "дом", gender: 0, enNoun: "house", nounHint: "house - дом",
    colors: {
      big: { en: "Big house", ruAdj: "Большой", hint: "big - большой" },
      new: { en: "New house", ruAdj: "Новый", hint: "new - новый" },
      blue: { en: "Blue house", ruAdj: "Синий", hint: "blue - синий" },
      white: { en: "White house", ruAdj: "Белый", hint: "white - белый" }
    }
  },
  {
    base: "телефон", gender: 0, enNoun: "phone", nounHint: "phone - телефон",
    colors: {
      black: { en: "Black phone", ruAdj: "Чёрный", hint: "black - чёрный" },
      new: { en: "New phone", ruAdj: "Новый", hint: "new - новый" },
      big: { en: "Big phone", ruAdj: "Большой", hint: "big - большой" }
    }
  },
  {
    base: "компьютер", gender: 0, enNoun: "computer", nounHint: "computer - компьютер",
    colors: {
      new: { en: "New computer", ruAdj: "Новый", hint: "new - новый" },
      big: { en: "Big computer", ruAdj: "Большой", hint: "big - большой" }
    }
  },
  {
    base: "мальчик", gender: 0, enNoun: "boy", nounHint: "boy - мальчик",
    colors: {
      big: { en: "Big boy", ruAdj: "Большой", hint: "big - большой" },
      small: { en: "Small boy", ruAdj: "Маленький", hint: "small - маленький" }
    }
  },

  // --- ЖЕНСКИЙ РОД (1) ---
  {
    base: "ручка", gender: 1, enNoun: "pen", nounHint: "pen - ручка",
    colors: {
      red: { en: "Red pen", ruAdj: "Красная", hint: "red - красный" },
      black: { en: "Black pen", ruAdj: "Чёрная", hint: "black - чёрный" },
      blue: { en: "Blue pen", ruAdj: "Синяя", hint: "blue - синий" },
      green: { en: "Green pen", ruAdj: "Зелёная", hint: "green - зелёный" },
      white: { en: "White pen", ruAdj: "Белая", hint: "white - белый" },
      pink: { en: "Pink pen", ruAdj: "Розовая", hint: "pink - розовый" }
    }
  },
  {
    base: "мышка", gender: 1, enNoun: "mouse", nounHint: "mouse - мышка (computer mouse)",
    colors: {
      red: { en: "Red mouse", ruAdj: "Красная", hint: "red - красный" },
      black: { en: "Black mouse", ruAdj: "Чёрная", hint: "black - чёрный" },
      white: { en: "White mouse", ruAdj: "Белая", hint: "white - белый" },
      grey: { en: "Grey mouse", ruAdj: "Серая", hint: "grey - серый" },
      big: { en: "Big mouse", ruAdj: "Большая", hint: "big - большой" },
      small: { en: "Small mouse", ruAdj: "Маленькая", hint: "small - маленький" }
    }
  },
  {
    base: "сумка", gender: 1, enNoun: "bag", nounHint: "bag - сумка",
    colors: {
      red: { en: "Red bag", ruAdj: "Красная", hint: "red - красный" },
      black: { en: "Black bag", ruAdj: "Чёрная", hint: "black - чёрный" },
      big: { en: "Big bag", ruAdj: "Большая", hint: "big - большой" },
      yellow: { en: "Yellow bag", ruAdj: "Жёлтая", hint: "yellow - жёлтый" }
    }
  },
  {
    base: "книга", gender: 1, enNoun: "book", nounHint: "book - книга",
    colors: {
      red: { en: "Red book", ruAdj: "Красная", hint: "red - красный" },
      big: { en: "Big book", ruAdj: "Большая", hint: "big - большой" },
      new: { en: "New book", ruAdj: "Новая", hint: "new - новый" }
    }
  },
  {
    base: "линейка", gender: 1, enNoun: "ruler", nounHint: "ruler - линейка",
    colors: {
      red: { en: "Red ruler", ruAdj: "Красная", hint: "red - красный" },
      blue: { en: "Blue ruler", ruAdj: "Синяя", hint: "blue - синий" },
      green: { en: "Green ruler", ruAdj: "Зелёная", hint: "green - зелёный" },
      big: { en: "Big ruler", ruAdj: "Большая", hint: "big - большой" }
    }
  },
  {
    base: "трава", gender: 1, enNoun: "grass", nounHint: "grass - трава",
    colors: {
      green: { en: "Green grass", ruAdj: "Зелёная", hint: "green - зелёный" }
    }
  },
  {
    base: "девочка", gender: 1, enNoun: "girl", nounHint: "girl - девочка",
    colors: {
      big: { en: "Big girl", ruAdj: "Большая", hint: "big - большой" },
      small: { en: "Small girl", ruAdj: "Маленькая", hint: "small - маленький" }
    }
  },

  // --- СРЕДНИЙ РОД (2) ---
  {
    base: "окно", gender: 2, enNoun: "window", nounHint: "window - окно",
    colors: {
      big: { en: "Big window", ruAdj: "Большое", hint: "big - большой" },
      small: { en: "Small window", ruAdj: "Маленькое", hint: "small - маленький" }
    }
  },
  {
    base: "море", gender: 2, enNoun: "sea", nounHint: "sea - море",
    colors: {
      blue: { en: "Blue sea", ruAdj: "Синее", hint: "blue - синий" },
      black: { en: "Black sea", ruAdj: "Чёрное", hint: "black - чёрный" },
      big: { en: "Big sea", ruAdj: "Большое", hint: "big - большой" }
    }
  },
  {
    base: "небо", gender: 2, enNoun: "sky", nounHint: "sky - небо",
    colors: {
      blue: { en: "Blue sky", ruAdj: "Голубое", hint: "blue - голубой" }
    }
  },
  {
    base: "солнце", gender: 2, enNoun: "sun", nounHint: "sun - солнце",
    colors: {
      yellow: { en: "Yellow sun", ruAdj: "Жёлтое", hint: "yellow - жёлтый" },
      orange: { en: "Orange sun", ruAdj: "Оранжевое", hint: "orange - оранжевый" }
    }
  },
  {
    base: "яблоко", gender: 2, enNoun: "apple", nounHint: "apple - яблоко",
    colors: {
      red: { en: "Red apple", ruAdj: "Красное", hint: "red - красный" },
      green: { en: "Green apple", ruAdj: "Зелёное", hint: "green - зелёный" }
    }
  }
]

const adjectiveForms = {
  red: { 0: "Красный", 1: "Красная", 2: "Красное" },
  black: { 0: "Чёрный", 1: "Чёрная", 2: "Чёрное" },
  blue: { 0: "Синий", 1: "Синяя", 2: "Синее" },
  green: { 0: "Зелёный", 1: "Зелёная", 2: "Зелёное" },
  yellow: { 0: "Жёлтый", 1: "Жёлтая", 2: "Жёлтое" },
  big: { 0: "Большой", 1: "Большая", 2: "Большое" },
  small: { 0: "Маленький", 1: "Маленькая", 2: "Маленькое" },
  new: { 0: "Новый", 1: "Новая", 2: "Новое" },
  white: { 0: "Белый", 1: "Белая", 2: "Белое" },
  pink: { 0: "Розовый", 1: "Розовая", 2: "Розовое" },
  orange: { 0: "Оранжевый", 1: "Оранжевая", 2: "Оранжевое" },
  grey: { 0: "Серый", 1: "Серая", 2: "Серое" }
}

const currentQuestion = ref(null)
const selectedOption = ref(null)
const isCorrect = ref(null)
const streak = ref(0)

const showPraiseModal = ref(false)
const currentPraise = ref({ ru: "", en: "" })

const praiseList = [
  { ru: "Ты умничка, Солиха! 🌟", en: "You are so smart, Solikha!" },
  { ru: "Ты молодец, Солиха! 🔥", en: "Way to go, Solikha!" },
  { ru: "Отличная работа, Солиха! ✨", en: "Great job, Solikha!" },
  { ru: "Так держать, Солиха! 💪", en: "Keep it up, Solikha!" }
]

const recentQuestions = []

function generateQuestion() {
  selectedOption.value = null
  isCorrect.value = null

  let attempts = 0
  let colorData, item

  // Пытаемся найти комбинацию, которой не было в последних 5 вопросах
  do {
    item = itemsDatabase[Math.floor(Math.random() * itemsDatabase.length)]
    const colorKeys = Object.keys(item.colors)
    const colorKey = colorKeys[Math.floor(Math.random() * colorKeys.length)]
    colorData = item.colors[colorKey]
    attempts++
    // Если вариантов мало или зациклилось, выходим после 10 попыток
  } while (recentQuestions.includes(colorData.en) && attempts < 10)

  // Запоминаем текущий вопрос в историю
  recentQuestions.push(colorData.en)
  if (recentQuestions.length > 5) {
    recentQuestions.shift() // Удаляем самый старый, держим размер в пределах 5
  }

  // Находим ключ цвета для этого элемента
  const colorKeyUsed = Object.keys(item.colors).find(key => item.colors[key].en === colorData.en)

  const correctPhrase = `${colorData.ruAdj} ${item.base}`
  const hintText = `${colorData.hint}, ${item.nounHint}`

  const wrongGenders = [0, 1, 2].filter(g => g !== item.gender)
  const wrongOptions = wrongGenders.map(g => {
    const adjForm = adjectiveForms[colorKeyUsed] ? adjectiveForms[colorKeyUsed][g] : colorData.ruAdj
    return `${adjForm} ${item.base}`
  })

  const options = [correctPhrase, ...wrongOptions].sort(() => Math.random() - 0.5)
  const correctIndex = options.indexOf(correctPhrase)

  currentQuestion.value = {
    en: colorData.en,
    hint: hintText,
    options,
    correctIndex
  }
}

function checkAnswer(index) {
  if (selectedOption.value !== null) return

  selectedOption.value = index
  if (index === currentQuestion.value.correctIndex) {
    isCorrect.value = true
    streak.value++

    if (streak.value === 5) {
      const randomPraise = praiseList[Math.floor(Math.random() * praiseList.length)]
      currentPraise.value = randomPraise
      showPraiseModal.value = true
      streak.value = 0
    } else {
      setTimeout(generateQuestion, 1000)
    }
  } else {
    isCorrect.value = false
    streak.value = 0
  }
}

function closePraise() {
  showPraiseModal.value = false
  generateQuestion()
}

generateQuestion()
</script>

<template>
  <div class="app-container">
    <header class="header">
      <div class="logo">🇷🇺 Russian Genders Trainer</div>
      <button 
        class="nav-btn" 
        @click="currentView = currentView === 'quiz' ? 'theory' : 'quiz'"
      >
        {{ currentView === 'quiz' ? '📚 Theory & Rules' : '✏️ Back to Practice' }}
      </button>
    </header>

    <!-- ЭКРАН 1: ТЕСТ-ТРЕНАЖЁР -->
    <main v-if="currentView === 'quiz'" class="quiz-main">
      <div class="streak-counter">
        🔥 Streak: <span>{{ streak }}/5</span>
      </div>

      <div class="card" v-if="currentQuestion">
        <h2 class="target-word">{{ currentQuestion.en }}</h2>
        <p class="word-hint">{{ currentQuestion.hint }}</p>

        <div class="options-grid">
          <button 
            v-for="(option, index) in currentQuestion.options" 
            :key="index"
            class="option-btn"
            :class="{
              'correct': selectedOption !== null && index === currentQuestion.correctIndex,
              'wrong': selectedOption === index && index !== currentQuestion.correctIndex
            }"
            @click="checkAnswer(index)"
          >
            {{ option }}
          </button>
        </div>

        <button 
          v-if="selectedOption !== null && !isCorrect" 
          class="next-btn"
          @click="generateQuestion"
        >
          Next Question ➡️
        </button>
      </div>
    </main>

    <!-- ЭКРАН 2: ТЕОРИЯ С РУССКИМИ НАЗВАНИЯМИ И АНГЛИЙСКИМ ОБЪЯСНЕНИЕМ -->
    <main v-else class="theory-main">
      <div class="theory-card">
        <h2>📖 Russian Genders: Complete Guide</h2>
        <p class="theory-intro">
          In the Russian language, every noun has a gender: <strong>Мужской род</strong> (Masculine), <strong>Женский род</strong> (Feminine), or <strong>Средний род</strong> (Neuter). Unlike English (where objects are usually "it"), Russian treats objects as "he", "she", or "it". 
        </p>
        <p class="theory-intro">
          When you describe an item with an adjective (like colors or sizes), <strong>the adjective must change its ending</strong> to match the gender of the noun!
        </p>
        
        <div class="gender-rule masculine">
          <h3>Мужской род (Masculine / Он)</h3>
          <p><strong>How to recognize:</strong> Nouns usually end with a <strong>consonant sound</strong> (like <em>-л, -н, -ш</em>).</p>
          <p><strong>Examples:</strong> стол (table), дом (house), карандаш (pencil).</p>
          <p class="rule-ex">✨ <strong>Adjective endings:</strong> <em>-ый</em> or <em>-ий</em><br>
          <em>Example:</em> Красн<strong>ый</strong> карандаш (Red pencil)</p>
        </div>

        <div class="gender-rule feminine">
          <h3>Женский род (Feminine / Она)</h3>
          <p><strong>How to recognize:</strong> Nouns usually end with the letters <strong>-а</strong> or <strong>-я</strong>.</p>
          <p><strong>Examples:</strong> ручка (pen), книга (book), сумка (bag).</p>
          <p class="rule-ex">✨ <strong>Adjective endings:</strong> <em>-ая</em> or <em>-яя</em><br>
          <em>Example:</em> Красн<strong>ая</strong> ручка (Red pen)</p>
        </div>

        <div class="gender-rule neuter">
          <h3>Средний род (Neuter / Оно)</h3>
          <p><strong>How to recognize:</strong> Nouns usually end with the letters <strong>-о</strong> or <strong>-е</strong>.</p>
          <p><strong>Examples:</strong> окно (window), море (sea), яблоко (apple).</p>
          <p class="rule-ex">✨ <strong>Adjective endings:</strong> <em>-ое</em> or <em>-ее</em><br>
          <em>Example:</em> Красн<strong>ое</strong> яблоко (Red apple)</p>
        </div>

        <div class="theory-tip">
          💡 <strong>Pro Tip:</strong> Always look at the <em>ending</em> of the noun to figure out its gender, and match the adjective's ending accordingly!
        </div>
      </div>
    </main>

    <!-- МОДАЛЬНОЕ ОКНО ПОХВАЛЫ -->
    <div v-if="showPraiseModal" class="modal-backdrop">
      <div class="modal-content">
        <h2>🌟 Awesome! 🌟</h2>
        <p class="praise-ru">{{ currentPraise.ru }}</p>
        <p class="praise-en">{{ currentPraise.en }}</p>
        <button class="modal-btn" @click="closePraise">Continue 🚀</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #2c3e50;
  background-color: #f8fafc;
  min-height: 100vh;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  padding-bottom: 12px;
  border-bottom: 2px solid #e2e8f0;
}

.logo {
  font-weight: bold;
  font-size: 1.1rem;
  color: #4f46e5;
}

.nav-btn {
  background: #4f46e5;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: background 0.2s;
}

.nav-btn:hover {
  background: #4338ca;
}

.streak-counter {
  text-align: right;
  font-size: 1rem;
  font-weight: 600;
  color: #d97706;
  margin-bottom: 12px;
}

.card {
  background: white;
  padding: 30px;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  text-align: center;
}

.target-word {
  font-size: 2rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 8px;
}

.word-hint {
  font-size: 0.95rem;
  color: #64748b;
  margin-bottom: 30px;
}

.options-grid {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.option-btn {
  background: #f1f5f9;
  border: 2px solid #e2e8f0;
  padding: 16px;
  font-size: 1.1rem;
  font-weight: 600;
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.2s;
  color: #334155;
}

.option-btn:hover:not(:disabled) {
  background: #e2e8f0;
  border-color: #cbd5e1;
}

.option-btn.correct {
  background: #dcfce7 !important;
  border-color: #22c55e !important;
  color: #166534 !important;
}

.option-btn.wrong {
  background: #fee2e2 !important;
  border-color: #ef4444 !important;
  color: #991b1b !important;
}

.next-btn {
  margin-top: 20px;
  background: #0ea5e9;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 1rem;
  font-weight: bold;
  border-radius: 8px;
  cursor: pointer;
}

.next-btn:hover {
  background: #0284c7;
}

/* Theory styles */
.theory-card {
  background: white;
  padding: 24px;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  line-height: 1.5;
}

.theory-card h2 {
  margin-bottom: 12px;
  color: #1e293b;
}

.theory-intro {
  color: #475569;
  margin-bottom: 12px;
  font-size: 0.95rem;
}

.gender-rule {
  margin-top: 18px;
  padding: 16px;
  border-radius: 10px;
}

.gender-rule.masculine { background: #eff6ff; border-left: 4px solid #3b82f6; }
.gender-rule.feminine { background: #fdf2f8; border-left: 4px solid #ec4899; }
.gender-rule.neuter { background: #f0fdf4; border-left: 4px solid #22c55e; }

.gender-rule h3 {
  margin-bottom: 6px;
  font-size: 1.05rem;
}

.gender-rule p {
  font-size: 0.9rem;
  color: #334155;
  margin-bottom: 6px;
}

.rule-ex {
  font-size: 0.9rem;
  color: #1e293b;
  margin-top: 8px;
  padding-top: 6px;
  border-top: 1px dashed rgba(0,0,0,0.1);
}

.theory-tip {
  margin-top: 20px;
  padding: 12px 16px;
  background: #fef3c7;
  border-left: 4px solid #f59e0b;
  border-radius: 8px;
  font-size: 0.9rem;
  color: #92400e;
}

/* Modal styles */
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 100;
}

.modal-content {
  background: white;
  padding: 30px;
  border-radius: 20px;
  text-align: center;
  max-width: 350px;
  width: 90%;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
  animation: popUp 0.3s ease;
}

.praise-ru {
  font-size: 1.3rem;
  font-weight: bold;
  color: #4f46e5;
  margin: 10px 0 5px 0;
}

.praise-en {
  font-size: 1rem;
  color: #64748b;
  margin-bottom: 20px;
}

.modal-btn {
  background: #4f46e5;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  font-weight: bold;
  border-radius: 8px;
  cursor: pointer;
}

@keyframes popUp {
  0% { transform: scale(0.8); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
</style>