
header {
    .logo {
        
    }
    
    .icons {

    }
}

SASS&LESS 라이브러리를 쓰면
위에 처럼  헤더 안에
예쁘고 코드양을 줄여줄수 있게끔 작성할 수 있다.


react를 쓰면 
PostCSS를 써서 모듈화하면서 쓸 수있다.





-webkit-line-clamp 속성
블록 컨테이너의 콘텐츠를 지정한 줄 수만큼으로 제한할 수 있는 속성
display 속성을 -webkit-box 또는 -webkit-inline-box로, 그리고 -webkit-box-orient 속성을 vertical로 설정한 경우에만 동작
단순히 요소의 줄 수만 제한하기 때문에 overflow: hidden 속성과 함께 사용하면 요소를 넘치는 텍스트를 감출 수 있다.
값
/* 키워드 값 */
-webkit-line-clamp: none;

/* <integer> 값 */
-webkit-line-clamp: 3;
-webkit-line-clamp: 10;

/* 전역 값 */
-webkit-line-clamp: inherit;
-webkit-line-clamp: initial;
-webkit-line-clamp: unset;

사용예
<div class="wrap">
    <div class="ellipsis">안녕하세요 안녕하세요 안녕하세요</div>
</div>
<div class="wrap">
    <div class="ellipsis">abcdefgeabcdegfdsa</div>
</div>

.wrap {
  width: 50px;
}

.ellipsis {
    display: -webkit-box;
    overflow: hidden;
    text-overflow: ellipsis;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
}

주의사항
영어문자 같은 경우 공백으로 구분되지 않은 문자의 경우 줄바꿈이 생기지 않기 때문에 word-break: break-all; 속성과 함께 사용하는 것이 좋다.
한 줄 말줄임 처리를 할 때 -webkit-line-clamp 속성과 text-align: right을 사용할 경우 폰트에 따라 말줄임 표시(...)가 나타나지 않을 때가 있는데 이를 방지하기 위해 단순히 한 줄 말처리를 위한 속성을 사용하는 것이 좋다.
.ellipsis {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}