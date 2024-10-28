<template>
    <div v-if="isVisible" class="popup-overlay">
      <div class="popup-content">
        <button class="close-btn" @click="$emit('close')">×</button>
        <h2>{{ profile.name }}</h2>
        <div class="profile-info">
          <div class="foodie-level">
            <strong>Foodie Level:</strong> {{ profile.level }}
          </div>
          <div class="bio">
            <strong>Bio:</strong><br>
            {{ profile.bio }}
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProfilePopup',
    props: {
      isVisible: Boolean,
      profile: Object
    }
  }
  </script>
  
  <style>
  .popup-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
    
  }
  
  .popup-content {
    background: rgb(0, 0, 0);
    padding: 20px;
    border-radius: 8px;
    position: relative;
    width: 300px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    height:auto;
    padding-bottom: 40px;
    color:white;
  }
  
  .popup-content h2 {
  color: white;
  margin-bottom: 15px;
    }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    border: none;
    background: none;
    font-size: 20px;
    cursor: pointer;
    color:aliceblue;
  }
  
  .profile-info {
    margin-top: 15px;
    
  }
  
  .foodie-level {
    margin-bottom: 10px;
  }

  .bio {
  color: white;
  line-height: 1.4;
}

.close-btn {
  margin-top: 20px;
  padding: 8px 16px;
  background: transparent;
  color: white;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.3s;
}

</style>