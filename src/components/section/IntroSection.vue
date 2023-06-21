<template>
  <section id="introSection" :class="attr">
    <h3 class="blind">과학의 분야 소개</h3>
    <div class="intro__inner container">
      <div class="intro__title">
        <span>science</span>
        <h3 v-html="title"></h3>
        <p v-html="desc"></p>
      </div>
      <div class="intro_desc">
        <div v-for="(text, index) in texts" v-bind:key="index">
          <h4 :class="'icon-bg' + (index + 1)">{{ text.title }}</h4>
          <p>
            {{ text.desc }}
          </p>
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
  data: function () {
    return {
      title: "과학의 <br />분야 소개",
      desc: "과학은 여러 가지 분야로 나뉘어지며,<br />다양한 주제와 문제를 다룹니다.<br />주요한 과학 분야의 일부는 다음과 같습니다.",
      texts: [
        {
          title: "물리학",
          desc: "물질의 성질, 운동, 에너지, 전자기학 등을 연구하는 학문입니다.물리학은 우주의 구조와 동작, 원자와 입자의 구성 등에 대한 이해를통해 기술 발전에도 많은 영향을 미칩니다.",
        },
        {
          title: "화학",
          desc: "물질의 성질, 구조, 구성, 반응 등을 연구하는 학문입니다. 화학은 우리 주변의 물질의 조합과 변화를 이해하고, 신약 개발, 재료 공학, 환경 보호 등에 중요한 역할을 합니다.",
        },
        {
          title: "생물학",
          desc: " 생명체의 구조, 기능, 발생, 진화 등을 연구하는 학문입니다. 생물학은 생명체의 동작 원리를 이해하고, 질병 치료, 식물 육성, 유전자 조작 등 다양한 분야에서 응용되고 있습니다.",
        },
        {
          title: "천문학",
          desc: "우주와 천체들의 구조, 운동, 성질 등을 연구하는 학문입니다. 천문학은 별과 은하의 형성과 진화, 우주의 기원과 구조에 대한 이해를 통해 우주항공 기술과 우주 탐사에도 영향을 미칩니다.",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import url(../../assets/scss/setting/mixins.scss);
//intro__wrap
.intro__wrap {
}
.intro__inner {
  display: flex;
  justify-content: space-between;
}
.intro__title {
  width: 33%;

  span {
    background-color: #ff3344;
    font-size: 14px;
    padding: 4px 30px 2px;
    color: #fff;
    border-radius: 40px;
    text-transform: uppercase;
    margin-bottom: 10px;
    display: inline-block;
  }
  h3 {
    font-size: 50px;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 30px;
  }
  p {
    font-size: 18px;
    line-height: 1.5;
    font-weight: 500;
  }
}
.intro_desc {
  width: 66%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  > div {
    width: 48%;
    margin-bottom: 40px;

    h4 {
      font-size: 24px;
      margin-bottom: 15px;
    }
    &:nth-child(3) {
      margin-bottom: 0;
    }

    &:nth-child(4) {
      margin-bottom: 0;
    }
  }
}
</style>
