
<template>
  <article class="tweet-card">
    <div class="tweet-header">
      <div class="avatar">
        {{ tweet.username.charAt(1).toUpperCase() }}
      </div>

      <div class="user-info">
        <strong>{{ tweet.name }}</strong>
        <span>{{ tweet.username }}</span>
      </div>
    </div>

    <p class="tweet-content">{{ tweet.content }}</p>

    <div class="tweet-date">
      {{ tweet.date }}
    </div>
  </article>
</template>

<script>
export default {
  name: 'TweetCard',
  props: {
    tweet: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.tweet-card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 14px;
  padding: 20px;
  transition: transform 0.2s, box-shadow 0.2s;
}

.tweet-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.06);
}

.tweet-header {
  display: flex;
  align-items: center;
  gap: 12px;
}

.avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #dbeafe;
  color: #2563eb;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

.user-info {
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.user-info span,
.tweet-date {
  color: #8993a4;
  font-size: 13px;
}

.tweet-content {
  color: #374151;
  line-height: 1.6;
  margin: 18px 0;
}

.tweet-date {
  border-top: 1px solid #f0f0f0;
  padding-top: 12px;
}
</style>
