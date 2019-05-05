<template lang="pug">
  .main-container
    .top
      .hero
        img.headshot(src="../assets/square-headshot.jpg" alt="head shot")
        span.quote
          h1.hello Hi, I'm Ben
          p.about I'm a Software Engineer in St. Petersburg, FL.
          img.tri(src="../assets/tri.png")
      .work
        img.work-item(v-for="item in work" :key="item.id" :src="require(`../assets/${item.image}`)")
    .bottom
      .article-container
        article.article(v-for="item in tech" :key="item.id")
          img.article-image(:src="require(`../assets/${item.image}`)")
          main.article-main
            header.article-header
              h2 {{ item.header }}
              p {{ item.date }}
            p {{ item.content }}
          button.keep-reading Keep Reading
</template>

<script>
import work from '../data/work.json'
import tech from '../data/tech.json'

export default {
  name: 'Main',
  data() {
    return {
      work: null,
      tech: null
    }
  },
  created() {
    this.work = work
    this.tech = tech
  }
}
</script>

<style lang="scss" scoped>
.top {
  background-image: url("../assets/space.png");
  background-size: cover;

  .hero {
    display: flex;
    padding-top: 100px;
    justify-content: center;
    margin-bottom: 50px;

    .quote {
      margin-right: 20px;
      background-color: #ffffff99;
      padding: 20px;
      height: 70px;
      border-radius: 5px;

      .tri {
        margin: auto;
        top: 210px;
        position: absolute;
        opacity: 0.6;
      }

      .hello {
        margin: 0 0 5px 0;
      }

      .about {
        margin: 0;
      }
    }

    .headshot {
      height: 200px;
      border-radius: 5px;
      margin: 20px;
    }
  }

  .work {
    background-color: #00000085;
    padding: 10px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    .work-item {
      padding: 10px;
    }
  }
}

.bottom {
  background-color: #000;
  padding: 20px;

  .article-container {
    
    .article {
      background-color: #fff;
      border-radius: 5px;
      margin-bottom: 20px;

      .article-image {
        height: 60px;
        width: 100%;
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
        object-fit: cover;
      }

      .article-main {
        padding: 20px;
        color: #0f0f0f;

        .article-header {
          display: flex;
          align-items: flex-end;

          h2 {
            margin: 0;
          }

          p {
            margin: 0 0 1px 10px;
          }
        }
      }

      .keep-reading {
        background-color: blue;
      }
    }
  }
}
</style>
