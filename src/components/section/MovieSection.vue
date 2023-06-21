<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner container">
      <div class="movie__text">
        <h3>영화 소개</h3>
        <p>다양한 과학 영화를 추천 하고 있습니다!</p>
        <router-Link to="/" class="button-blue">자세히보기</router-Link>
      </div>
      <div class="movie__item">
        <div>
          <img src="@/assets/images/movie/movie01.png" alt="무비이미지1" />
        </div>
        <div>
          <img src="@/assets/images/movie/movie02.png" alt="무비이미지2" />
        </div>
        <div>
          <img src="@/assets/images/movie/movie03.png" alt="무비이미지3" />
        </div>
        <div>
          <img src="@/assets/images/movie/movie04.png" alt="무비이미지4" />
        </div>
        <div>
          <img src="@/assets/images/movie/movie05.png" alt="무비이미지5" />
        </div>
        <div>
          <img src="@/assets/images/movie/movie06.png" alt="무비이미지6" />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: {
      type: String,
      required: true,
    },
  },
};
</script>
<style lang="scss">
//movie__section
.movie__wrap {
  overflow: hidden;
}
.movie__inner {
  height: 1100px;
}
.movie__text {
  h3 {
    font-size: 50px;
    margin-bottom: 40px;
  }
  p {
    font-size: 22px;
    font-weight: 300;
    margin-bottom: 30px;
  }
  a {
    margin: 50px 0;
    border-radius: 50px;
  }
}

.movie__item {
  @include flex-between;
  position: absolute;
  margin-top: 70px;

  > div {
    width: 400px;
    margin-right: 10px;
    img {
      width: 100%;
    }
  }
}

//movie__page
.movie__page {
}
.movie__slider {
  display: none;
}
.movie__search {
  text-align: center;
  margin-bottom: 50px;

  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    @include border(50px);
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#f7100d, #fff);
    @include border(50px);
  }
}
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100;
    margin-bottom: 50px;
    li {
      a {
        border: 1px solid #f7100d;
        padding: 10px 20px;
        margin: 0 10px;
        color: #f7100d;
      }
    }
  }
}
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    li {
      width: 19.333%;
      margin-bottom: 2%;

      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}
</style>
