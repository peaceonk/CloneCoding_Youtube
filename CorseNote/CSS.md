CSS
===
참고 : https://www.youtube.com/watch?v=67stn7Pu7s4
---

<hr>

-   HTML 파일에서는 되도록 정보만 담도록한다.
>제어문(JS같은)은 따로 작성하는 것이 로드에도/유지보수에도 좋다

<hr>

-   css 모듈화 공부
>css도 다른 언어와 마찬가지로 상단에 변수를 선언해주고 그 변수로 제어하면 유지보수에 편리함.(color , padding ...)
> <pre><code>
> header {
>    .logo {
>        
>    }
>    
>    .icons {
>
>    }
> }
> </code></pre>
>
> SASS&LESS 라이브러리를 쓰면
> 위에 처럼  헤더 안에
> 예쁘고 코드양을 줄여줄수 있게끔 작성할 수 있다.
>
> react를 쓰면 
> PostCSS를 써서 모듈화하면서 쓸 수있다.
>
> 반응형 시 화면 크기에 따른 제어
> <pre><code>@media screen and (min-width:768px){}</code></pre>
>
>
- CSS 속성
> # css 텍스트 줄 수 고정  
> <code>-webkit-line-clamp</code> 속성 : 
>
>블록 컨테이너의 콘텐츠를 지정한 줄 수만큼으로 제한할 수 있는 속성  
>display 속성을 <code>-webkit-box</code> 또는 <code>-webkit-inline-box</code>로,  
>그리고 <code>-webkit-box-orient</code> 속성을 vertical로 설정한 경우에만 동작  
>단순히 요소의 줄 수만 제한하기 때문에  
><code>overflow: hidden</code> 속성과 함께 사용하면 요소를 넘치는 텍스트를 감출 수 있다.
>
>/* 키워드 값 */   
> <pre><code>-webkit-line-clamp: none;</code></pre>
>
>
>/* <_integer> 값 */   
> <pre><code>-webkit-line-clamp: 3;
> -webkit-line-clamp: 10;</code></pre>
>
>/* 전역 값 */   
> <pre><code>-webkit-line-clamp: inherit;
> -webkit-line-clamp: initial;
>-webkit-line-clamp: unset;</code></pre>
>
>
> ?
> <pre><code>
>.wrap {
>  width: 50px;
>}
>
>.ellipsis {
>    display: -webkit-box;
>    overflow: hidden;
>    text-overflow: ellipsis;
>    -webkit-box-orient: vertical;
>    -webkit-line-clamp: 2;
>}
> </code></pre>
>주의사항    
>
>영어문자 같은 경우 공백으로 구분되지 않은 문자의 경우 줄바꿈이 생기지 않기 때문에 
> <code> word-break: break-all;</code>
> 속성과 함께 사용하는 것이 좋다.
>한 줄 말줄임 처리를 할 때 <code> -webkit-line-clamp</code> 속성과
><code>text-align: right </code>을 사용할 경우 폰트에 따라 말줄임 표시(...)가 나타나지 않을 때가 있는데 이를 방지하기 위해 단순히 한 줄 말처리를 위한 속성을 사용하는 것이 좋다.
> <pre><code>
>.ellipsis {
>  overflow: hidden;
>  text-overflow: ellipsis;
>  white-space: nowrap;
>}
> </code></pre>
>