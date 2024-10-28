<template>
  <div id="leftside"></div>
  <div id="rightside">
    <div id="container" class="container">
      <div class="row">
        <div class="col">
          <Header />
          <Navigation />
        </div>
      </div>
      <div class="row">
        <div class="col-md-3">
          <img src="/images/chili.jpg" alt="White Chicken Chili" class="img-fluid" />
        </div>
        <div class="col-md-9">
          <h2 class="text-success">COMMENTS</h2>
          <BlogComments :comments="comments" />
        </div>
      </div>
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Navigation from './components/Navigation.vue'
import BlogComments from './components/BlogComments.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Navigation,
    BlogComments,
    Footer
  },
  data() {
    return {
      comments: [
        {
          author: 'Brianna',
          date: 'February 18, 2021 @ 3:30 pm',
          content: 'Was amazing! My Walmart didn\'t have coriander in stock and didn\'t have ground cumin. I used serrano instead of jalapeño. It was just like my favorite tortilla soup from BJs. I am sending this recipe to my family. I want everyone to try it!'
        },
        {
          author: 'LINH',
          date: 'February 15, 2021 @ 9:46 am',
          content: 'I just made this soup today and it\'s so tasty! didn\'t have corn at home but still turned out very good. It\'s a winner! I made beef chili for my parents; but since my dad has gout he can\'t eat beef; this white chicken chili is perfect for him. Thank you Lisa!'
        },
        {
          author: 'CATHERINE LEONARDO',
          date: 'February 13, 2021 @ 12:58 pm',
          content: 'I LOVE this White Chicken Chili! You are right, it is satiating meal---delicious with toasted bread. Refreshingly different taste than any chicken chili I\'ve made in the past. I made it exactly as written and added some chopped zucchini, carrots, and celery. Instead of shredding the chicken, I chopped it into small pieces. It freezes very well. Will be an all-time favorite, for sure.'
        },
        {
          author: 'KALI',
          date: 'February 13, 2021 @ 11:31 am',
          content: 'This recipe is dynamite! My partner usually won\'t eat beans but he finished the whole pot (darn was hoping to have some for leftovers haha). This is crowd-pleaser that I am going to add to my regular recipe rotation. Thanks so much, Lisa!'
        }
      ]
    }
  }
}
</script>

<style>
* {
    font-family: Arial, Helvetica, sans-serif;
    margin: 0;
    padding: 0;
}

#leftside {
    float: left;
    width: 35%;
    height: 300vh;
    background-color: rgb(77, 192, 154);
}

#rightside {
    float: left;
    width: 65%;
    height: 300vh;
    background-color: rgb(238, 226, 192);
    position: relative;
}

#container {
    background-color: rgba(255, 255, 255, 0.8); 
    position: absolute;
    top: 45%;            
    left: 25%;         
    transform: translate(-50%, -50%); 
    width: 120%;         
    min-height: 80vh;  
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1); 
}

h2 {
    color: rgb(77, 192, 154);
    margin: 20px 0;
    text-transform: uppercase;
}

img {
    width: 100px;
    height: auto;
    margin: 10px 0;
}

.header {
    font-family: 'Sacramento', cursive;
    color: rgb(216, 150, 7);
    font-size: 2em;
    padding: 10px 0;
}
</style>