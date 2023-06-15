# Sprite 과제

## 구조 설계
![contents](/images/img.png "contents")

## Image Sprite
이미지 스프라이트(image sprite)란 여러 개의 이미지를 하나의 이미지로 합쳐서 관리하는 이미지를 의미합니다.

sprite 태그는 이미지 태그사용시 성능을 위해서 사용합니다.
이미지 스프라이트(image sprite)를 사용하면 이미지를 다운받기 위한 서버 요청을 단 몇 번으로 줄일 수 있습니다.
모바일 환경과 같이 한정된 자원을 사용하는 플랫폼(platform)에서는 웹 페이지의 로딩 시간을 단축해주는 효과가 있습니다.
또한, 많은 이미지 파일을 관리하는 대신 몇 개의 스프라이트 이미지(sprite image) 파일만을 관리하면 되므로 매우 간편합니다.

### Image Sprite 사용법
1. srite 태그에 이미지를 지정합니다.
2. 지정된 하나의 이미지를 background-position 값으로 위치이동 시켜 여러번 사용합니다. 
```
// srite 태그에 이미지를 지정합니다.
.sprite{
  background: url(/images/rank.png) no-repeat;
}
// 지정된 하나의 이미지를 background-position 값으로 위치이동 시켜 여러번 사용합니다. 
.item1{
  background-position: 100% 6px;
}
.item2{
  background-position: 100% -34px;
}
.item3{
  background-position: 100% -12px;
}
.item4{
  background-position: 100% 8px;
}
```
## counter-increment
ol li 숫자 리스트 태그에서 숫자를 지우고 원하는 스타일대로 숫자를 꾸미고 싶을때 사용합니다.

### counter-increment 사용법
1. counter-reset 를 ol 태그에 지정해줍니다. 이때 counter-reset 은 혹시 모를 오류 방지용이며 필수값은 아닙니다.
2. counter-increment 의 이름을 지정하여 li 태그에 선언해줍니다.
3. li 요소에 차례대로 content: counter 값을 입력해 주어 숫자가 차례로 올라가도록합니다.
```
ol{
  /* counter-reset 은 혹시모를 오류 방지용이며 필수값은 아님. */
  counter-reset: number;
}
// counter-increment 의 이름을 number 로 지정하였습니다.
ol li{
  counter-increment: number;
}
// li 요소에 차례대로 content: counter(number) 를 지정해 주어 숫자가 차례로 올라가도록 하였습니다.
li::before{
  content: counter(number);
}
li::before{
  content: counter(number);
}
li::before{
  content: counter(number);
}
li::before{
  content: counter(number);
}
```

## Position 을 활용한 "더보기" 버튼
.more 더보기 버튼에 position: absolute 를 주고 상위 div container box 에 position: relative 를 주어 기준을 container 로 지정되게 하였습니다. 
```
.favorite{
  position: relative;
}
.more{
  position: absolute;
}
```

## 완성 이미지
![contents](/images/스크린샷_2023-06-14_오후_5.29.38.png "contents")