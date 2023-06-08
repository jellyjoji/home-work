# position

마크업 순서
1. 로그인(제목)
2. 아이디 레이블과 입력서식
3. 비밀번호 레이블과 입력서식
4. 로그인 버튼
5. 회원가입 및 아이디/비밀번호 찾기 링크 


## form 태그 
#### fieldset
fieldset 요소는 관련 있는 폼 필드 세트(form FIELD SET)를 표시한다. 폼 필드 세트는 폼 내에서 관련 컨트롤을 하나의 그룹으로 묶은 것을 말한다. 이때 legend 요소를 함께 사용해야 한다.
#### legend
fieldset 요소의 제목(LEGEND)을 표시한다. fieldset 요소를 이용하여 여러 개의 컨트롤들을 묶었으면 이 묶음이 어떤 성격 또는 용도인지 알려줄 필요가 있으며, 이때 legend 요소를 사용한다.
이 요소를 사용하면 fieldset 요소로 묶인 영역 주변에 테두리 선이 나타난다.
```
<form action="/" class="login-form" method="POST">
  <fieldset>
    <legend class=".a11yHidden">로그인</legend>
  </fieldset>
</form>
```
#### .a11yHidden
접근성 향상을 위해 제목을 legend 에 추가한 후 .a11yHidden 클래스 속성을 주어 눈에 보이지 않지만 숨겨진 정보를 전달할수 있게 설계하였다. 
````g
<legend class=".a11yHidden">로그인</legend>
````
````
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
````
## 목록 태그
#### ul 
비순차 목록(Unordered List) 요소
#### ol 
순차 목록(Ordered List) 요소
#### li 
목록 항목(List Item) 요소
목록 요소 중 ul 비순차 목록(Unordered List) 요소와 li 목록 항목(List Item) 요소를 사용하여 회원가입 및 아이디/비밀번호 찾기 링크를 설계하였다.
````
<ul class="extraContainer">
  <li class="signUp">
    <a href="/"> <strong>&gt</strong> 회원가입</a>
  </li>
  <li class="findIdPw">
    <a href="/"> <strong>&gt</strong> 아이디 비밀번호 찾기</a>
  </li>
</ul>
````
## position
#### position : static;
마크업한 순서대로 보여주는 정적인 상태이며 기본 속성이다.
#### position : absolute;
어떤 요소든 position : absolute; 주면 독립적인 block 으로 렌더된다. 가장 가까운 position : relative 요소를 기준으로 삼는다.
#### position : relative;
static 하게 붙어있던 로고를 살짝 띄워서 움직일수있는 상태로 변경한다. 지금 현재 위치를 기준으로 한다.
***
상위 container 태그에 position: relative; 를 주고 하위 loginBtn 태그에 position: absolute; 을 주고 container 를 기준으로 loginBtn 위치가 변경되도록 하였다.
```
<div class="container">
  <div class="loginInput">
    <!-- id  -->
    <div class="id">
      <label for="id">아이디</label>
      <input type="text" class="" id="id" placeholder="euid@euid.dev" required />
    </div>
    <!-- pw -->
    <div class="pw">
      <label for="pw">비밀번호</label>
      <input type="password" class="" id="pw" placeholder="8자리 이상" required />
    </div>
  </div>
  <!-- button -->
  <button type="submit" class="loginBtn">로그인</button>
</div>
```
```
.container {
  position: relative;
  padding: 0.5rem;
}
.loginBtn {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  width: 50px;
  height: 53px;
  border: none;
  font-size: var(--font-small);
  color: var(--font-white);
  border-radius: var(--border-radius);
  background: var(--login-backgrond);
}
```


<img width="755" alt="스크린샷_2023-06-07_오후_4 30 53" src="https://github.com/jellyjoji/home-work/assets/74365275/5d3066ef-163f-4890-94a8-12c9e002ebd1">
