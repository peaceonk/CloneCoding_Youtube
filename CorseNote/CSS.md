CSS
===
참고 : https://www.youtube.com/watch?v=67stn7Pu7s4
---

<hr>

-   HTML 파일에서는 되도록 정보만 담도록한다.
> 제어문(JS같은)은 따로 작성하는 것이 로드에도/유지보수에도 좋다.  
> HTML emmet : (알고있던 거지만)  
> 태그명(.클래스명)>자식엘리먼트${엘리먼트에 들어갈 텍스트}*반복할 횟수  
> 띄워쓰기하면 안됨
> 
> 예시
> <pre>
>   div.container>div.item.item4{content$}*10  
> </pre>
> 결과   
> ```
>   <div class="container">
>        <div class="item item4">content1</div>
>        <div class="item item4">content2</div>
>        <div class="item item4">content3</div>
>        <div class="item item4">content4</div>
>        <div class="item item4">content5</div>
>        <div class="item item4">content6</div>
>        <div class="item item4">content7</div>
>        <div class="item item4">content8</div>
>        <div class="item item4">content9</div>
>        <div class="item item4">content10</div>
>    </div>
>```
> 
<hr>

#   CSS 모듈화
>css도 다른 언어와 마찬가지로 상단에 변수를 선언해주고 그 변수로 제어하면 유지보수에 편리함.(color , padding ...)
> ```
> header {
>    .logo {
>        
>    }
>    
>    .icons {
>
>    }
> }
> ```
>
> SASS&LESS 라이브러리를 쓰면  
> 위와 같이  헤더 안에
> 예쁘고 코드양을 줄여줄 수 있다.
>
> react를 쓰면 
> PostCSS를 써서 모듈화하면서 쓸 수있다.
>
> 반응형 시 화면 크기에 따른 제어
> <pre><code>@media screen and (min-width:768px){}</code></pre>
>

<br>

# CSS 속성
> - css 텍스트 줄 수 고정  
> <code>-webkit-line-clamp</code> 속성 : 
>블록 컨테이너의 콘텐츠를 지정한 줄 수만큼으로 제한할 수 있는 속성  
>display 속성을 <code>-webkit-box</code> 또는 <code>-webkit-inline-box</code>로,  
>그리고 <code>-webkit-box-orient</code> 속성을 vertical로 설정한 경우에만 동작  
>단순히 요소의 줄 수만 제한하기 때문에  
><code>overflow: hidden</code> 속성과 함께 사용하면 요소를 넘치는 텍스트를 감출 수 있다.
>
>- 키워드 값   
> <pre><code>-webkit-line-clamp: none;</code></pre>
>
>
>- `<integer>` 값  
> <pre>-webkit-line-clamp: 3;
> -webkit-line-clamp: 10;</pre>
>
>- 전역 값 
> <pre>-webkit-line-clamp: inherit;
> -webkit-line-clamp: initial;
>-webkit-line-clamp: unset;</-webkit-line-clamp:></pre>
>
>
> - TODO: ?
> <pre>
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
></pre>
>
> <br>
> 
>주의사항    
>
>영어문자 같은 경우 공백으로 구분되지 않은 문자의 경우 줄바꿈이 생기지 않기 때문에 
> <code> word-break: break-all;</code>
> 속성과 함께 사용하는 것이 좋다.
>한 줄 말줄임 처리를 할 때 <code> -webkit-line-clamp</code> 속성과
><code>text-align: right </code>을 사용할 경우 폰트에 따라 말줄임 표시(...)가 나타나지 않을 때가 있는데 이를 방지하기 위해 단순히 한 줄 말처리를 위한 속성을 사용하는 것이 좋다.
> <pre>
>.ellipsis {
>  overflow: hidden;
>  text-overflow: ellipsis;
>  white-space: nowrap;
>}
> </pre>

<br>


# CSS 기본기
> df   
> df

<br>


# CSS Gird
>  
> 1. <code>flex</code> 등장  
> 과거에 많이 레이아웃을 잡기위해 많이 쓰던   
> <code>float</code>의 본래 목적은 컨텐츠 내에서 이미지와 텍스트의 레이아웃을 잡는 목적이었다.  
> 하지만 BOX의 레이아웃을 잡을만한 기능이 없었기 때문에,  
> <code>float</code> 을 이용해서 그 일을 하였고   
> 그렇기 때문에 레이아웃을 구성하는데 매우 불편하고 시간이 오래 걸리고 유연함이 떨어지고 불가능한 레이아웃 또한 유지보수에도 좋지 않았다.
> 
> 여기서! <code>flex</code>가 등장하게 되는데
> <code>flex</code>를 통해서 Gird를 할 수 있다(?)   
> 
> ---
> 2. <code>flex</code>의 속성   
> - **container**에 적용할 수있는 flex의 속성  
> <code>display</code> :  
> <code>flex-direction</code> :  
> <code>flex-wrap</code> :   
> <code>flex-flow</code> :    
> <code>justify-content</code> :  
> <code>align-items</code> :  
> <code>flex-content</code> :  
>
> <br>
>
> - container내의 **item**에 적용할 수있는 flex의 속성  
> <code>order</code> :  
> <code>flex-grow</code> :  
> <code>flex-shrink</code> :  
> <code>flex</code> :    
> <code>align-self</code> : 
>
>
>  ---
> 3. <code>flex</code>의 중심축 개념(?)  
>  <code>element</code> 들을 가로(X축)를 기준으로 혹은 세로(Y축)을 기준으로 나열하게 되는 중심축 개념이 있다.   
> 



<br>

연습을 통해 익히는게 가장 좋음.
---