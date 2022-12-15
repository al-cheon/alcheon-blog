# 웹페이지 렌더링

<aside>
💡  ref. 드림코딩

</aside>

[서버사이드 렌더링 (개발자라면 상식으로 알고 있어야 하는 개념 정리 ⭐️)](https://www.youtube.com/watch?v=iZ9csAfU5Os&t=83s)

## 웹페이지 타임라인

1. SSR - 1990년도
정적인 페이지를 서버에서 불러와 클라이언트에 표시
2. iframe 태그 도입 - 1996
문서내에 문서를 담을 수 있게 됨
3. XMLHttpRequest (fetch API의 원조) - 1998
HTML문서 전체가 아니라 JSON 포멧으로 서버에서 가볍게 데이터만 가져올수 있게 됨
가져온 데이터를 JS를 이용해서 동적으로 HTML요소를 생성해서 표시
4. AJAX - 2005
Gmail, Google Maps 와같은 웹 애플리케이션이 나오면서
SPA (Single Page Application) 가 쓰이기 시작
5. CSR
JS가 표준화가 잘 되면서 Angular, React, Vue 같은 프래임워크가 나오면서 CSR 시대가 오게된다
6. SSR (* CSR 특징 참조)
CSR의 문제점때문에 다시 SSR이 도입이 되었다
서버에서 만들어진 정적인 HTML문서와 동적인 요소를 제어하는 JS파일을 이용한다

### CSR 특징

- 장점
- 단점
    1. Initial Loading may take too long
    사용자가 첫 화면을 보기까지 시간이 걸린다
    2. Low SEO (Search Engine Optimization)
    Google, Naver 와 같은 검색엔진들은 각 웹 사이트의 HTML을 Web crawlers, 분석해서 우리가 빠르게 검색할 수 있게 도와주는데,
    CSR에서 사용되어지는 HTML의 <body> 는 대부분 텅텅 비어있기 때문에 검색엔진들이 웹 페이지를 분석하는데 어려움이 있다

### SSR 특징

- 장점 ::  * CSR 단점의 반대
    1. Initial page load is faster
    첫 페이지 로딩이 빨라짐
    2. Great SEO
    효율적인 SEO 가능
- 단점
    1. Blinking issue, Non-rich site interactions
    static 사이트 고유의 문제점
    클릭 할때마다 페이지가 다시 서버에서 만들어지는 UE(User Experience) 를 이용자에게 주게된다
    2. Server side overhead
    사용자가 많을 수록 서버에 과부하가 걸리기 쉽다 → 느려진다
    3. Need to wait before interacting (* TTV, TTI 참고)
    사용자가 빠르게 웹 사이트를 확인할 수는 있지만, 동적으로 처리되는 JS를 아직 다운받지 못해서 클릭했는데 반응이 없는 경우가 생길 수 있다
    

### TTV, Time To View / TTI, Time To Interact

보여지기까지 시간 / 반응까지 되는 시간