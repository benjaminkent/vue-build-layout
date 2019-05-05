<template lang="pug">
  .main-container
    .top
      .hero
        img.headshot(src="../assets/square-headshot.jpg" alt="head shot")
        span.quote
          h1.hello Hey, I'm Ben
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
            p.content {{ item.content }}
          button.keep-reading Keep Reading
      .stay-connected-container
        h3.connect Stay connected with me.
        span.social
          i.fab.fa-twitter
          i.fab.fa-instagram
          i.fab.fa-facebook-f
          i.fab.fa-github
    footer.footer
      p.footer-content
        | 2019 Benjamin Kent Jehl
      p.footer-content
        | Made with
        i.fas.fa-heart
        | in St Petersburg, FL.
        a(href="https://benjaminkent.io" target="_blank")
          | benjaminkent.io
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
  background-color: #030016;
  padding: 20px;

  .article-container {
    
    .article {
      background-color: #fff;
      border-radius: 5px;
      margin-bottom: 30px;
      padding-bottom: 25px;

      .article-image {
        height: 60px;
        width: 100%;
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
        object-fit: cover;
      }

      .article-main {
        padding: 20px 20px 5px 20px;
        color: #0f0f0f;

        .content {
          margin-bottom: 0;
        }

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
        background-color: #007FE8;
        color: #fff;
        position: absolute;
        font-size: 20px;
        font-weight: bold;
        padding: 7px;
        border-radius: 5px;
        border: none;
        right: 50px;
        cursor: pointer;
      }
    }
  }

  .stay-connected-container {
    margin-top: 70px;
    display: flex;
    flex-direction: column;
    align-items: center;

    .connect {
      color: #fff;
      font-size: 20px;
    }

    .social {
      font-size: 32px;
      cursor: pointer;

      i {
        margin: 0 15px;
      }

      .fa-twitter {
        color: #47A2ED;
      }

      .fa-instagram {
        color: #F93452;
      }

      .fa-facebook-f {
        color: #627EBA;
      }

      .fa-github {
        color: #fff;
      }
    }
  }
}

.footer {
  padding: 125px 0 20px 0;
  background-color: #030016;
  display: flex;
  flex-direction: column;
  align-items: center;

  .footer-content {
    color: #f4f4f4;
    margin: 2px 0;

    a {
      color: #f4f4f4;
      text-decoration: none;
      margin-left: 5px;
    }

    .fa-heart {
      color: red;
      margin: 0 4px;
    }
  }
}
</style>
