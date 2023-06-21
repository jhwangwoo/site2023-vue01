<template>
  <footer id="footer" className="footer__wrap bg-blue jamsil" role-lever="3">
    <div className="footer__inner container">
      <div className="footer__text">
        <h5>Jung hwang woo</h5>
        <p>
          궁금한 사항의 메일로 연락 해주세요!
          <br />
          <router-Link to="mailto:ghkddn132@gmail.com">
            ghkddn132@gmail.com
          </router-Link>
        </p>
        <ul className="sns">
          <li>
            <router-Link to="/">
              <span className="ir"></span>
            </router-Link>
          </li>
          <li>
            <router-Link to="/">
              <span className="ir"></span>
            </router-Link>
          </li>
          <li>
            <router-Link to="/">
              <span className="ir"></span>
            </router-Link>
          </li>
          <li>
            <router-Link to="/">
              <span className="ir"></span>
            </router-Link>
          </li>
          <li>
            <router-Link to="/">
              <span className="ir"></span>
            </router-Link>
          </li>
        </ul>
      </div>
      <div className="footer__menu">
        <div>
          <h4>사이트</h4>
          <ul>
            <li>
              <router-Link to="/">웹표준 사이트</router-Link>
            </li>
            <li>
              <router-Link to="/">반응형 사이트</router-Link>
            </li>
            <li>
              <router-Link to="/">패럴랙스 사이트</router-Link>
            </li>
            <li>
              <router-Link to="/">포트폴리오 사이트</router-Link>
            </li>
          </ul>
        </div>
        <div>
          <h4>유형</h4>
          <ul>
            <li>
              <router-Link to="/">이미지 유형</router-Link>
            </li>
            <li>
              <router-Link to="/">카드 유형</router-Link>
            </li>
            <li>
              <router-Link to="/">이미지/텍스트 유형</router-Link>
            </li>
            <li>
              <router-Link to="/">배너 유형</router-Link>
            </li>
            <li>
              <router-Link to="/">텍스트 유형</router-Link>
            </li>
            <li>
              <router-Link to="/">푸터 유형</router-Link>
            </li>
          </ul>
        </div>
        <div>
          <h4>스크립트</h4>
          <ul>
            <li>
              <router-Link to="/">검색 이펙트</router-Link>
            </li>
            <li>
              <router-Link to="/">퀴즈 이펙트</router-Link>
            </li>
            <li>
              <router-Link to="/">마우스 이펙트</router-Link>
            </li>
            <li>
              <router-Link to="/">슬라이드 이펙트</router-Link>
            </li>
            <li>
              <router-Link to="/">패랠랙스 이펙트</router-Link>
            </li>
            <li>
              <router-Link to="/">게임 이팩트</router-Link>
            </li>
          </ul>
        </div>
        <div>
          <h4>레퍼런스</h4>
          <ul>
            <li>
              <router-Link to="/">CSS</router-Link>
            </li>
            <li>
              <router-Link to="/">FONTS</router-Link>
            </li>
            <li>
              <router-Link to="/">BLOG</router-Link>
            </li>
            <li>
              <router-Link to="/">REFERENCE</router-Link>
            </li>
            <li>
              <router-Link to="/">TUTORIAL </router-Link>
            </li>
          </ul>
        </div>
      </div>
      <div className="footer__right">
        Copyright 2023. All Rights Reserved. - Designed by Jung hwang woo
      </div>
    </div>
  </footer>
</template>

<style lang="scss">
.footer__wrap {
  padding-top: 50px;
}

.footer__inner {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  .footer__text {
    width: 25%;

    h5 {
      font-size: 18px;
      margin-bottom: 15px;
    }
    p {
      padding-top: 5px;
      a {
        text-decoration: underline;
        text-underline-position: under;
      }
      font-weight: 300;
      font-size: 14px;
      margin-bottom: 15px;
    }
    .sns {
      display: flex;
      li {
        a {
          width: 45px;
          height: 45px;
          background-color: #e9e9e9;
          border-radius: 50px;
          margin-right: 10px;
          display: flex;
          justify-content: center;
          background-position: center;
          background-repeat: no-repeat;
        }
        &:nth-child(1) a {
          background-image: url(../../assets/images/footer/footersns01.svg);
        }
        &:nth-child(2) a {
          background-image: url(../../assets/images/footer/footersns02.svg);
        }
        &:nth-child(3) a {
          background-image: url(../../assets/images/footer/footersns03.svg);
        }
        &:nth-child(4) a {
          background-image: url(../../assets/images/footer/footersns04.svg);
        }
        &:nth-child(5) a {
          background-image: url(../../assets/images/footer/footersns05.svg);
        }
      }
    }
  }

  .footer__menu {
    width: 75%;
    display: flex;
    justify-content: space-between;

    > div {
      width: 25%;
      h4 {
        font-size: 18px;
        margin-bottom: 15px;
      }

      ul {
        li {
          font-weight: 300;
          font-size: 14px;
          line-height: 1.5;
        }
      }
    }
  }

  .footer__right {
    width: 100%;
    padding: 30px;
    text-align: center;
    border-top: 1px solid #e5e5e5;
    margin-top: 50px;
    color: #808080;
    font-size: 14px;
  }
}
</style>
