<template>

    <div class="home-page">

      <b-card class="about home-page-item" style="border-radius:3%">
        <h3 class="about-myself"> About Myself </h3>
        <p>Hello, I am Arun Vijay, from Coimbatore. A student of Electronics and Communication Engineering at Amrita School of Engineering. I work on Embedded systems and Digital electronics.
          I like working on software on a variety of platforms, and I am looking for job opportunities in the Electronics Engineering sector.</p>
      </b-card>

      <b-card class="home-page-item" style="border-radius:3%">
        <h3 class="about-myself"> Education </h3>
        <ul>
          <li>
            <p>Bachelor's Degree <br>
              Amrita School of Engineering, Coimbatore, (8.78 CGPA)</p>
          </li>
          <li>
            <p>Higher Secondary <br>
              G.D Matriculation School, Coimbatore, (84%)</p>
          </li>
          <li>
            <p>Senior Secondary<br>
              Carmel Garden Matriculation Higher Secondary School, Coimbatore, (97.4%)</p>
          </li>
        </ul>
      </b-card>

      <b-card class="about home-page-item" style="border-radius:3%">
        <h3 class="about-myself"> Work experience </h3>
        <ul>
          <li>
            <p>Intern at Spark Drives and automation, Coimbatore (April - May 2019). <br>
              Role: Worked on a simple software prototype for a vending machine on Raspberry-Pi.</p>
          </li>
        </ul>
      </b-card>

      <nuxt-link :to="{ name: 'slug', params: {slug: skills.slug} }" class="home-page-item" style="color:rgb(233, 68, 101); border-radius:3%; max-width: 25%">
        <b-card :title=skills.title img-src="~/static/arduino.jpg" align="center">
          <b-card-text>
            {{skills.description}}
          </b-card-text>
        </b-card>
      </nuxt-link>

    </div>
</template>

<script>
export default {
  async asyncData({ $content, params}) {
    const article = await $content('work', params.slug)
      .only(['title', 'description', 'slug'])
      .where({tags: 'skills'})
      .fetch();
    const skills = article[0];
    const about = await $content('work', params.slug)
      .where({tags: 'about'})
      .fetch();
    return {skills, about};

  }
}
</script>

<style>

.home-page-item{
  display: block;
  padding: 20px;
  vertical-align: middle;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  max-width: 70%;
  margin-top:5%;
  margin-bottom: 5%;
}

.home-page{
  display:inline-block;
  margin-left: auto;
  margin-right: auto;
  justify-content: center;
}

.about {
    text-align: left;
}

.about-myself{
    padding-top: 2rem;
    font-size: 3rem;
    text-align: center;
    font-family:georgia;
    font-weight: bold;
    color: mediumvioletred;
}
p{
  font-size: 1.5rem;
  font-family: Ubuntu;
  text-align: left;
}
</style>
