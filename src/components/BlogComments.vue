<template>
  <div id="blogposts" class="section">
    <div v-for="(comment, index) in comments" :key="index" class="post">
      <div class="comment-header">
        <img 
          :src="'/images/profile.png'" 
          class="profile-pic" 
          @click="showProfile(comment.author)"
        />
        {{ comment.author }} — {{ comment.date }} REPLY
      </div>
      <div class="comment-content">
        {{ comment.content }}
      </div>
    </div>
    <ProfilePopup 
      :is-visible="showPopup" 
      :profile="selectedProfile"
      @close="closeProfile"
    />
  </div>
</template>

<script>
import ProfilePopup from './ProfilePopup.vue'

export default {
  name: 'BlogComments',
  components: {
    ProfilePopup
  },
  props: {
    comments: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      showPopup: false,
      selectedProfile: null,
      profiles: {
        'Brianna': {
          name: 'Brianna',
          level: 'Novice',
          bio: 'Food enthusiast. Love to cook and experiment. Into only organic, fat free, sugar free stuffs!'
        },
        'LINH': {
          name: 'LINH',
          level: 'Newcomer',
          bio: 'Love food! Grew up with meat and potatoes. Recently venture outside my comfort zone. Loving everything I have been eating so far. Thai is my favorite at this time.'
        },
        'CATHERINE LEONARDO': {
          name: 'CATHERINE LEONARDO',
          level: 'Mentor',
          bio: 'I have to say I never was the adventurous type until 2 years ago. My boyfriend, who is of Japanese background, exposed me to other cultural food and I have never look back since!'
        },
        'KALI': {
          name: 'KALI',
          level: 'Novice',
          bio: "Food is my passion. So is cooking. I love to experiment and try new things. I have to admit I'm a food whore! Invite me over for dinner and I'll be there!"
        },
      }
    }
  },
  methods: {
    showProfile(author) {
      this.selectedProfile = this.profiles[author]
      this.showPopup = true
    },
    closeProfile() {
      this.showPopup = false
      this.selectedProfile = null
    }
  }
}
</script>

<style>
.profile-pic {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin-right: 10px;
  cursor: pointer;
  vertical-align: middle;
}

.post {
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 15px;
    margin: 10px 0;
    background-color: white;
}

.comment-header {
    margin-bottom: 10px;
    display: flex;
    align-items: center;
}

.comment-content {
    line-height: 1.4;
    margin-left: 40px;
}
</style>