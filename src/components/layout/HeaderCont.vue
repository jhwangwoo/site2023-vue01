<template>
  <header
    id="header"
    class="header__wrap jamsil9 bg-blue"
    riole="heading"
    role-level="1"
  >
    <div class="header__inner container">
      <div class="header__logo">
        <router-Link to="/"> jung <em>site</em> </router-Link>
      </div>
      <nav class="header__nav" role="navigation">
        <ul>
          <li>
            <router-Link to="/intro">소개</router-Link>
          </li>
          <li>
            <router-Link to="/port">노벨상 수상</router-Link>
          </li>
          <li>
            <router-Link to="/youtube">유튜브</router-Link>
          </li>
          <li>
            <router-Link to="/unsplash">이미지</router-Link>
          </li>
          <li>
            <router-Link to="/movie">영화</router-Link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss">
//header__wrap
.header__wrap {
}
.header__inner {
  text-align: center;
  .header__logo {
    width: 100%;
    font-size: 30px;

    a {
      font-size: 30px;
      display: inline-block;
      padding: 5px;
      margin: 5px;
      text-transform: uppercase;
      font-weight: 800;

      em {
        display: inline-block;
        padding: 10px;
        margin: 2px;
        text-transform: lowercase;
        font-weight: 500;
      }
    }
  }
  .header__nav {
    width: 100%;
    ul {
      padding: 0 10%;
      display: flex;
      justify-content: space-between;
    }
    li {
      a {
        display: inline-block;
        padding: 5px 5px 8px 5px;
        margin: 5px 5px 8px 5px;
        position: relative;

        &::before {
          content: "";
          width: calc(100% - 20px);
          height: 2px;
          background-color: var(--color_body);
          position: absolute;
          left: 10px;
          bottom: 5px;
          transform: scaleX(0);
          transition: all 0.3s ease;
        }

        &:hover::before {
          transform: scaleX(1);
        }
      }
    }
  }
}
</style>

<!-- <script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script> -->
