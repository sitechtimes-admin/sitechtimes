<template>
  <div class="flex items-center justify-center h-screen bg-gray-100">
    <Navbar />
    <div class="global-container">
      <!-- <NuxtLink class="block" v-for="homepage in homepages" :to="`/articles/${homepage.slug}`" :key="homepage.slug">
    {{ homepage.title }}
    </NuxtLink> -->
    <h3 class="section-title">Trending Articles</h3>
    <section class="trending-section">
    <CardComponent 
    articleUrl="https://www.thetravel.com/best-surfing-spots-california/" author="Daniel Briskman" published="Jan 21, 2021" category="sports" imageTitle="A Girl Surfing" title="Girl almost eaten by shark but makes friends with shark and then betrays it and rides it like a surfboard." class="trending-main"/>
    <div class="trending-sides">
      <CardComponent 
      articleUrl="https://www.thetravel.com/best-surfing-spots-california/" author="Daniel Briskman" published="Jan 21, 2021" category="sports" imageTitle="A Girl Surfing" title="Girl almost eaten by shark but makes friends with shark and then betrays it and rides it like a surfboard." class="trending-side trending-sub"/>
      <CardComponent 
      articleUrl="https://www.thetravel.com/best-surfing-spots-california/" author="Daniel Briskman" published="Jan 21, 2021" category="sports" imageTitle="A Girl Surfing" title="Girl almost eaten by shark but makes friends with shark and then betrays it and rides it like a surfboard." class="trending-side"/>
    </div>
    </section>
    <h3 class="section-title">News</h3>
    <section class="news-section">
      <text-below-article-preview articleUrl="https://theconversation.com/us/topics/rocket-science-195" author="Daniel Briskman" published="Jan 31, 2020" category="news" imageAlt="Space X Rocket" title="I hate rockets, and this is why you should too" imageUrl="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNAu-JntINSfv0U6b2Df439C-cXbDOOYRzsj9UuhMwwP290pnObcSbtJHXo93jNBpA5Ys&usqp=CAU" class="news-preview"/>
      <text-below-article-preview articleUrl="https://theconversation.com/us/topics/rocket-science-195" author="Daniel Briskman" published="Jan 31, 2020" category="news" imageAlt="Space X Rocket" title="I hate rockets, and this is why you should too" imageUrl="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNAu-JntINSfv0U6b2Df439C-cXbDOOYRzsj9UuhMwwP290pnObcSbtJHXo93jNBpA5Ys&usqp=CAU" class="news-preview news-sub"/>
      <text-below-article-preview articleUrl="https://theconversation.com/us/topics/rocket-science-195" author="Daniel Briskman" published="Jan 31, 2020" category="news" imageAlt="Space X Rocket" title="I hate rockets, and this is why you should too" imageUrl="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNAu-JntINSfv0U6b2Df439C-cXbDOOYRzsj9UuhMwwP290pnObcSbtJHXo93jNBpA5Ys&usqp=CAU" class="news-preview"/>
    </section>
    <h3 class="section-title">Politics</h3>
    <h3 class="section-title">Entertainment</h3>
    <h3 class="section-title">Opinion</h3>
    <h3 class="section-title">Science</h3>
    <h3 class="section-title">Activities</h3>
    </div>
    <Footer />
  </div>
</template>

<script>
export default {
    data() {
      return {
        homepages: []
      }
    },
    async mounted() {
      const homepages = await this.$axios.get('/articles/homepage');
      this.homepages = homepages.data;
    }
  }
</script>

<style lang="scss">
.section-title {
  margin: 5rem 0;
}
.trending-section {
  display: flex;
  flex-flow: row wrap;
}
.trending-main {
  width: 670px;
  height: 550px;
}
.trending-side {
  margin-left: 3rem;
  height: 260px;
  width: 450px;
}
.trending-sub {
  margin-bottom: 3rem;
}
.news-section {
  display: flex;
}
.news-preview {
  width: 350px;
}
.news-sub {
  margin: 0 3.8rem;
}
</style>