<template>
  <section id="portSection" :class="attr">
    <h3>노벨상 수상</h3>
    <p>
      혁신적인 연구를 수행한 과학자들에게 수여되며, 여러 인물들이 이 영예를
      안았습니다.
    </p>
    <div class="port__inner container">
      <div class="port__btn">
        <ul>
          <li><router-Link to="/">물리학</router-Link></li>
          <li><router-Link to="/">화학</router-Link></li>
          <li><router-Link to="/">생물학</router-Link></li>
          <li><router-Link to="/">천문학</router-Link></li>
        </ul>
      </div>
      <div class="port__cont">
        <div class="port" v-for="(text, index) in texts" v-bind:key="index">
          <figure class="port__header">
            <img :src="text.img" :alt="text.title" />
          </figure>
          <div class="port__body">
            <span>
              <img :src="text.icon" :alt="text.title" />
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
      title: "과학의 <br />분야 소개",
      desc: "과학은 여러 가지 분야로 나뉘어지며,<br />다양한 주제와 문제를 다룹니다.<br />주요한 과학 분야의 일부는 다음과 같습니다.",
      texts: [
        {
          title: "알버트 아인슈타인",
          desc: "상대성 이론",
          img: "./images/port/portbg01.png",
          icon: "./images/member/member48.svg",
        },
        {
          title: "마리 퀴리",
          desc: "방사선의 성질에 대한 연구",
          img: "./images/port/portbg02.png",
          icon: "./images/member/member30.svg",
        },
        {
          title: "마리오 빌라르 베르트",
          desc: "스핀 트랜지스터 개발에 대한 연구",
          img: "./images/port/portbg03.png",
          icon: "./images/member/member06.svg",
        },
        {
          title: "앨버트 민츠",
          desc: "마그네토-히드로다이나믹 발전기 개발",
          img: "./images/port/portbg04.png",
          icon: "./images/member/member07.svg",
        },
        {
          title: "마크스 퀴스",
          desc: "양자 정보 이론 개발",
          img: "./images/port/portbg05.png",
          icon: "./images/member/member08.svg",
        },
        {
          title: "마이클 코스테이니",
          desc: "유도 이온화에 대한 실험과 이론 연구",
          img: "./images/port/portbg06.png",
          icon: "./images/member/member09.svg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import url(../../assets/scss/setting/mixins.scss);
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
