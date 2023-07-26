 <h1>vue.js를 이용해서 사이트를 만들어보앗습니다</h1>

[vuesiteLink](https://jhw2023-vue-site.netlify.app/)

![이미지](https://raw.githubusercontent.com/jhwangwoo/site2023-vue01/main/public/images/vue_img.png)

 <h1>API 사용 방법</h1>

<p>useEffect: 함수형 컴포넌트에서 부수 효과(side effect)를 수행할 수 있는 React 훅입니다. 컴포넌트의 라이프사이클에 따른 동작을 정의하거나 외부 데이터를 가져올 수 있습니다. </p>

<p>useState: 함수형 컴포넌트에서 상태(state)를 추가하고, 해당 상태 값을 업데이트하는 React 훅입니다. 상태값을 가지고 동적으로 컴포넌트를 업데이트하고 관리할 수 있습니다.</p>

<p>fetch와 async/await: 웹 API를 사용하여 서버로부터 데이터를 가져오는 방법 중 하나로, 비동기 처리를 위해 사용됩니다. fetch 함수는 Promise를 반환하고, async/await는 비동기 코드를 동기 코드처럼 작성할 수 있게 도와줍니다.</p>

  <h2>영화 정보 애플리케이션</h2>
  <p>사용한 API: TMDb (The Movie Database) API</p>

[TMDb](https://www.themoviedb.org/?language=ko)

  <p>
    이 API는 영화 정보를 제공하는데 사용되었습니다. TMDb API를 활용하여 인기 영화, 검색 결과 및 영화 태그와 관련된 정보를 가져왔습니다.
    <br>
    TMDb API를 호출할 때는 `api_key`와 쿼리를 URL에 추가하여 영화 데이터를 요청했습니다.
  </p>

  <h2>이미지 애플리케이션</h2>
  <p>사용한 API: Unsplash API</p>

[Unsplash](https://unsplash.com/developers)

  <p>
    이 API는 이미지 정보를 제공하는데 사용되었습니다. Unsplash API를 활용하여 이미지 검색 결과와 이미지 태그를 가져왔습니다.
    <br>
    Unsplash API를 호출할 때는 `client_id`와 쿼리를 URL에 추가하여 이미지 데이터를 요청했습니다.
  </p>

  <h2>YouTube 비디오 애플리케이션</h2>

[youtube](https://developers.google.com/youtube/v3?hl=ko)

  <p>사용한 API: YouTube Data API</p>
  <p>
    이 API는 YouTube 비디오 정보를 제공하는데 사용되었습니다. YouTube Data API를 활용하여 영상 검색 결과를 가져왔습니다.
    <br>
    YouTube Data API를 호출할 때는 `api_key`와 쿼리를 URL에 추가하여 비디오 데이터를 요청했습니다.
  </p>

  <h1>내용</h1>

  <h2>영화 정보 애플리케이션</h2>
  <p> 영화 관련 애플리케이션으로, TMDb API를 활용하여 인기 영화, 검색 결과, 그리고 영화 태그와 관련된 정보를 알려줍니다.</p>

  <h2>이미지 애플리케이션</h2>
  <p>이미지 관련 애플리케이션으로, Unsplash API를 활용하여 이미지 검색 결과와 이미지 태그를 가져와서 보여줍니다</p>

  <h2>YouTube 비디오 애플리케이션</h2>
  <p>YouTube 비디오 관련 애플리케이션으로, YouTube Data API를 활용하여 비디오 검색 결과를 가져와서 보여줍니다.</p>
