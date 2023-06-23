<template>
  <section id="membersSection" :class="attr">
    <h3>유명 과학자 소개</h3>
    <div class="members__inner">
      <p>기술 발전에 한 획을 그은 역사적인 분들을 소개합니다!</p>
      <div class="member__inner container">
        <div class="member">
          <figure class="member__header">
            <img src="@/assets/images/member/member01.png" alt="맴버1" />
          </figure>
          <div class="member__body">
            <router-Link to="/" class="btn">업적 보기</router-Link>
          </div>
        </div>
        <div class="member">
          <figure class="member__header">
            <img src="@/assets/images/member/member02.png" alt="맴버1" />
          </figure>
          <div class="member__body">
            <router-Link to="/" class="btn">업적 보기</router-Link>
          </div>
        </div>
        <div class="member">
          <figure class="member__header">
            <img src="@/assets/images/member/member03.png" alt="맴버1" />
          </figure>
          <div class="member__body">
            <router-Link to="/" class="btn">업적 보기</router-Link>
          </div>
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
.members__wrap {
  h3 {
    margin-bottom: 10px;
  }
}
.member__inner {
  @include flex-between;

  .member {
    margin-top: 50px;
    width: 32%;

    .member__header {
      border: 2px solid var(--color_body);
      img {
        width: 100%;
      }
    }
    .member__body {
      padding: 15px 10px;
      background: #000;
      color: #fff;
      z-index: 100;
      position: relative;
      h4 {
        font-size: 22px;
      }

      a {
        color: #fff;
        text-decoration: underline;
        text-underline-position: under;
      }
    }
  }
}
</style>
