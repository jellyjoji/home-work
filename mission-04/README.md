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

## CSS
해당 프로젝트의 미션은 Grid 속성 사용하기입니다. display: grid; 속성을 적용하여 grid-template-row, grid-template-columns, gap 요소를 사용하였습니다.

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
```
.container {
  /* grid 사용 */
  padding: 2rem 0;
  display: grid;
  grid-template-columns: auto auto;
}
.subContainer {
  /* background: lime; */
  display: grid;
  grid-template-rows: auto auto auto;
  gap: 0.5rem;
}
```
## 완성 이미지
![news 1](https://github.com/jellyjoji/home-work/assets/74365275/44720fbb-6e93-46ef-b565-3f066e2d1147)



