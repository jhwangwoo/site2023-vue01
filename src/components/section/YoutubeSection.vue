<template>
  <section id="youtubeSection" :class="attr">
    <div class="youtube__inner container">
      <div class="youtube__text">
        <h3>과학 유튜브 소개</h3>
        <p>신비로운 과학으 재미있게 볼수 있는 유튜브를 소개 합니다!</p>
        <router-Link to="/" class="button-red">자세히보기</router-Link>
      </div>
      <div class="youtube__item">
        <div>
          <img
            src="@/assets/images/youtube/youtube01.png"
            alt="유튜브이미지1"
          />
        </div>
        <div>
          <img
            src="@/assets/images/youtube/youtube02.png"
            alt="유튜브이미지2"
          />
        </div>
        <div>
          <img
            src="@/assets/images/youtube/youtube03.png"
            alt="유튜브이미지3"
          />
        </div>
        <div>
          <img
            src="@/assets/images/youtube/youtube04.png"
            alt="유튜브이미지4"
          />
        </div>
        <div>
          <img
            src="@/assets/images/youtube/youtube05.png"
            alt="유튜브이미지5"
          />
        </div>
        <div>
          <img
            src="@/assets/images/youtube/youtube06.png"
            alt="유튜브이미지6"
          />
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
@import "../../assets/scss/setting/mixins.scss";

.youtube__wrap {
  overflow: hidden;
}
.youtube__inner {
  height: 600px;
}
.youtube__text {
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

.youtube__item {
  display: flex;
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

.youtube__page {
}
.youtube__search {
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
.youtube__tag {
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
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    li {
      width: 31.333%;
      margin-bottom: 4%;

      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}
</style>
