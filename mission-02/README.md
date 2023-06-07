# position

마크업 순서
1. 로그인(제목)
2. 아이디 레이블과 입력서식
3. 비밀번호 레이블과 입력서식
4. 로그인 버튼
5. 회원가입 및 아이디/비밀번호 찾기 링크 


## form 태그 
#### fieldset
fieldset 요소는 관련 있는 폼 필드 세트(form FIELD SET)를 표시한다. 폼 필드 세트는 폼 내에서 관련 컨트롤을 하나의 그룹으로 묶은 것을 말한다.
폼을 효과적으로 계층화시킬 수 있다. 이때 legend 요소를 함께 사용해야 한다.
#### legend
fieldset 요소의 제목(LEGEND)을 표시한다. fieldset 요소를 이용하여 여러 개의 컨트롤들을 묶었으면 이 묶음이 어떤 성격 또는 용도인지 알려줄 필요가 있으며, 이때 legend 요소를 사용한다.
이 요소를 사용하면 fieldset 요소로 묶인 영역 주변에 테두리 선이 나타난다.

```
<form action="/" class="login-form" method="POST">
    <fieldset>
      <legend>로그인</legend>
    </fieldset>
</form>
```
## position
#### position : static;
마크업한 순서대로 보여주는 정적인 상태.
#### position : absolute;
요소를 띄어 올린다.
어떤요소든 position : absolute; 주면 독립적인 block 으로 렌더된다.
#### position : relative
static 하게 붙어있던 로고를 살짝 띄워서 움직일수있는 상태로 변경.
```
/* fieldset 에 라인 없애기주기 */
fieldset{
  border: none;  
}
/* position 의 상위 기준 static */
.extraContainer{
  display: inline;
  /* position: static; */
}
.signUp{
  display: inherit;
}
/* 부모를 기준으로 배치되도록 position: relative  설정 */
.findIdPw{
  position: relative;
  display: inherit;
  padding-left: 0.5rem;
}
```


<img width="755" alt="스크린샷_2023-06-07_오후_4 30 53" src="https://github.com/jellyjoji/home-work/assets/74365275/5d3066ef-163f-4890-94a8-12c9e002ebd1">
