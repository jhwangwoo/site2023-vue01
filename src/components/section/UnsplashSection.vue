<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner container">
      <div class="unsplash__text">
        <h3>과학 이미지 다운로드 추천</h3>
        <p>다양한 이미지를 다운로드 받고 싶다면 여기서 받으세요!</p>
        <router-Link to="/" class="button-blue">자세히보기</router-Link>
      </div>
      <div class="unsplash__item">
        <div>
          <img
            src="@/assets/images/unsplash/unsplash01.png"
            alt="언스플이미지1"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash02.png"
            alt="언스플이미지2"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash03.png"
            alt="언스플이미지3"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash04.png"
            alt="언스플이미지4"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash05.png"
            alt="언스플이미지5"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash06.png"
            alt="언스플이미지6"
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
//unsplash__section
.unsplash__wrap {
  overflow: hidden;
}
.unsplash__inner {
  height: 600px;
}
.unsplash__text {
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

.unsplash__item {
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

//unsplash__page
.unsplash__page {
}
.unsplash__slider {
  display: none;
}
.unsplash__search {
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
.unsplash__tag {
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
.unsplash__cont {
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
