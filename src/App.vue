
<template>
  <main class="app">
    <header class="top-header">
      <h1>TweetSpace</h1>
      <p>Share your thoughts with the world.</p>
    </header>

    <section class="tweets-section">
      <div class="section-header">
        <div>
          <h2>Latest Tweets</h2>
          <p>Explore what everyone is talking about.</p>
        </div>

        <button @click="toggleView" class="toggle-button">
          {{ isGridView ? '☰ List View' : '▦ Grid View' }}
        </button>
      </div>

      <div :class="['tweets-container', isGridView ? 'grid-view' : 'list-view']">
        <TweetCard
          v-for="tweet in tweets"
          :key="tweet.id"
          :tweet="tweet"
        />
      </div>
    </section>

    <footer>
      W13B - Vue Grid/List View Assignment
    </footer>
  </main>
</template>

<script>
import TweetCard from './components/TweetCard.vue'

export default {
  name: 'App',

  components: {
    TweetCard
  },

  data () {
    return {
      isGridView: true,

      tweets: [
        {
          id: 1,
          name: 'Alex Johnson',
          username: '@alexjohnson',
          content: 'Just finished working on my Vue project! Learning something new every day. 🚀',
          date: 'November 9, 2026'
        },
        {
          id: 2,
          name: 'Sarah Williams',
          username: '@sarahw',
          content: 'Beautiful weather today! Perfect day to get outside and enjoy life. ☀️',
          date: 'November 8, 2026'
        },
        {
          id: 3,
          name: 'Michael Brown',
          username: '@michaelb',
          content: 'Finally understood how Vue components and props work. Coding is getting easier!',
          date: 'November 7, 2026'
        },
        {
          id: 4,
          name: 'Emily Davis',
          username: '@emilydavis',
          content: 'Never stop learning, never stop growing. Small progress every day adds up.',
          date: 'November 6, 2026'
        },
        {
          id: 5,
          name: 'James Wilson',
          username: '@jamesw',
          content: 'Working on a new website today. Really enjoying web development!',
          date: 'November 5, 2026'
        },
        {
          id: 6,
          name: 'Olivia Martin',
          username: '@oliviam',
          content: 'Your future is created by what you do today, not tomorrow. 💙',
          date: 'November 4, 2026'
        }
      ]
    }
  },

  methods: {
    toggleView () {
      this.isGridView = !this.isGridView
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f3f6fb;
  color: #172033;
}

.app {
  min-height: 100vh;
}

.top-header {
  background: #172554;
  color: white;
  padding: 40px 20px;
  text-align: center;
}

.top-header h1 {
  margin: 0 0 10px;
  font-size: 36px;
}

.top-header p {
  margin: 0;
  color: #cbd5e1;
}

.tweets-section {
  max-width: 1100px;
  margin: 40px auto;
  padding: 0 20px;
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  margin-bottom: 25px;
}

.section-header h2 {
  margin: 0 0 7px;
  font-size: 25px;
}

.section-header p {
  margin: 0;
  color: #718096;
}

.toggle-button {
  background: #2563eb;
  color: white;
  border: none;
  border-radius: 9px;
  padding: 12px 18px;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
}

.toggle-button:hover {
  background: #1d4ed8;
}

.tweets-container {
  display: grid;
  gap: 18px;
}

.grid-view {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}

.list-view {
  grid-template-columns: 1fr;
}

footer {
  text-align: center;
  padding: 25px;
  color: #8993a4;
  font-size: 13px;
}

@media (max-width: 650px) {
  .grid-view {
    grid-template-columns: 1fr;
  }

  .section-header {
    align-items: flex-start;
    flex-direction: column;
  }
}
</style>
