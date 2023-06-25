<template>
  <section id="portSection" :class="attr">
    <h3>과학자 소개</h3>
    <p>
      과학자들은 지식의 산다리와 혁신의 선구자로, 인류의 이해를 넓히고 세계를
      변화시키는 역할을 수행합니다.
    </p>
    <div class="port__inner container">
      <div class="port__btn">
        <ul>
          <li><router-Link to="/port">더 보기</router-Link></li>
        </ul>
      </div>
      <div class="port__cont">
        <div class="port" v-for="(text, index) in texts" v-bind:key="index">
          <figure class="port__header">
            <img :src="text.portImg" :alt="text.title" />
          </figure>
          <div class="port__body">
            <span>
              <img :src="text.iconImg" :alt="text.title" />
            </span>
            <div class="desc">
              <h4>{{ text.title }}</h4>
              <p>{{ text.desc }}</p>
            </div>
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
  data: function () {
    return {
      texts: [
        {
          portImg: "images/port/Jean-PierreSauvage.png",
          iconImg: "images/member/member11.svg",
          title: "장 피에르 소바주",
          desc: "분자 기계와 나노기계의 개발",
        },
        {
          portImg: "images/port/NielsBohr.png",
          iconImg: "images/member/member41.svg",
          title: "니콜라스 쿱른",
          desc: "원자 구조와 양자역학",
        },
        {
          portImg: "images/port/NikolaTesla.png",
          iconImg: "images/member/member45.svg",
          title: "니콜라 테슬라",
          desc: "교류 전력 시스템의 개발",
        },
        {
          portImg: "images/port/MarieCurie.png",
          iconImg: "images/member/member30.svg",
          title: "마리 퀴리",
          desc: "방사선의 성질에 대한 연구",
        },
        {
          portImg: "images/port/isaacNewton.png",
          iconImg: "images/member/member40.svg",
          title: "이사크 뉴턴",
          desc: "만유인력의 법칙",
        },
        {
          portImg: "images/port/AlbertEinstein.png",
          iconImg: "images/member/member48.svg",
          title: "알버트 아인슈타인",
          desc: "상대성 이론",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
.port__wrap {
  h3 {
    margin-bottom: 10px;
  }
  p {
  }
}
.port__inner {
  .port__btn {
    ul {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
      li {
        a {
          border: 1px solid #8da7e9;
          padding: 20px 50px;
          margin-right: 10px;
          background: #d9e4ff;
          border-radius: 50px;

          &:hover {
            background-color: darken(#d9e4ff, 10%);
          }
        }
      }
    }
  }
  .port__cont {
    @include flex-between;

    flex-wrap: wrap;
    .port {
      width: 32.222%;
      margin-top: 30px;
      .port__header {
        img {
          width: 100%;
        }
      }
      .port__body {
        display: flex;
        margin-top: 8px;
        > span {
          width: 50px;
          height: 50px;
          border-radius: 50%;
          background-color: #ce7f7f;
          overflow: hidden;
          img {
            margin-top: 8px;
            width: 50px;
            height: 50px;
          }
        }
        .desc {
          padding-left: 10px;
          text-align: left;
          > h4 {
            font-size: 20px;
            line-height: 1.6;
          }
          > p {
            font-size: 16px;
            font-weight: 400;
            color: #2c3a4b;
          }
        }
      }
    }
  }
}
</style>
