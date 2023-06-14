# GRID 과제

## HTML Mark up 
main 안에서 header 과 container 로 나누어 
header 에는 h2 title 제목을 명시해주었고,
container 에는 image 와 subContainer 컨텐츠로 분리하였습니다.

// main>*(header>h1+.container>(figure+dl))

### figure
figure 는 사진,도표,비디오, 코드 등을 담는 컨테이너 역할입니다.
### figcaption
figcaption 는 이에 대한 설명 문구를 담는 태그입니다. 
```
      <figure class="thumbNail">
        <img src="/images/news 1.png" alt="W3C renew" />
        <figcaption>W3C 리뉴얼</figcaption>
      </figure>
```

### dl dt dd
dl은 설명 목록 요소입니다.
dt은 용어 제목 요소입니다.
dd은 용어 설명 요소입니다.
#### ul li 와 dt dd 의 차이는?
ul li 는 여러개일때 사용하기 용이하며,
dt dd 는 가급적 1:1 대응할때 사용합니다. 주로 이름과 값을 쓸때 사용합니다.
```
      <dl class="subContainer">
        <dt class="subTitle"><strong>W3C 사이트가 리뉴얼 되었습니다.</strong></dt>
        <dd class="subDesc">
          디자인 및 다양한 view 환경을 고려하여 구성되어 있으며, 기존보다 최신 정보 및 개발자를 위한 기술 가이드도 찾기 쉽도록 구성되어 있습니다.
        </dd>
      </dl>
```
### time
날짜 및 시간 요소를 타나낼때 사용합니다.
```
<time datetime="2023-05-19">May 19. 2023</time>
```

## CSS
해당 프로젝트의 미션은 Grid 속성 사용하기입니다. display: grid; 속성을 적용하여 grid-template-row, grid-template-columns, gap 요소를 사용하였습니다.

### .a11yHidden
모든 컨텐츠에는 제목을 써줘야 하며 그 제목을 보이지 않게 숨길때 a11yHidden 클래스를 사용합니다.
```
<h2 class="a11yHidden">숨긴 제목</h2>

/* Accessibility Styles */
.a11yHidden,
legend {
  overflow: hidden;
  position: absolute !important;
  clip: rect(0, 0, 0, 0);
  clip-path: inset(50%);
  width: 1px;
  height: 1px;
  margin: -1px;
}
```

### :root 가상클레스선택자
공통적으로 사용할 속성 스타일을 지정하여 일괄 변경에 편리하도록 하였습니다. 공통 색상, 폰트크기, 외각, 그림자 등을 지정할수습니다.
```
:root {
  --color-primary: #ED552F;
  --color-gray: rgb(163, 163, 163);

  --font-md: 14px;

  --border-radius: 5px;
}
```
## 그리드 레이아웃 Grid Layout
### grid-template-row, grid-template-columns
그리드 영역의 행(Row)과 열(Column)을 설정합니다. 이때 각 영역의 크기를 지정할 수 있습니다.
### gap, row-gap, column-gap
그리드 레이아웃에서도 간격을 조정할 때 사용합니다.
### grid-template-areas
grid-area로 명명된 요소를 템플릿 영역에 배치할 수 있으며 명명된 이름을 여러 번 사용하여 다중 행이나 다중 열이 병합된 형태로 사용할 수 있습니다.
title, date, summary, thumbnail 콘텐츠에 grid-area 를 부여하여 grid-template-areas 에 활용하였습니다.
```
.news-item {
  margin-top: 35px;
  display: grid;
  grid-template-columns: 115px 1fr;
  grid-template-rows: auto;
  gap: 2rem;
  grid-template-areas:
    "thumbnail title"
    "thumbnail date"
    "thumbnail summary";
}

.news-item-title {
  grid-area: title;
  margin: 0;
}

.news-item-date {
  grid-area: date;
}

.news-item-summary {
  grid-area: summary;
}

.news-item-thumbnail {
  grid-area: thumbnail;
  margin: 0;
  text-align: center;
}
```
## 완성 이미지
<img width="755" alt="스크린샷_2023-06-12_오후_5 00 13" src="https://github.com/jellyjoji/home-work/assets/74365275/0d48fdcf-79cb-4aa6-a4fc-215240da6bac">




