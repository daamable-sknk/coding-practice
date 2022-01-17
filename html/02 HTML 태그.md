> 기본 강의 구성 
> > [부스트코스](https://www.boostcourse.org/)의 [비전공자를 위한 HTML/CSS](https://www.boostcourse.org/cs120)
> 참고 자료
> > 개발자를 위한 웹 기술 : [HTML: Hypertext Markup Language](https://developer.mozilla.org/ko/docs/Web/HTML)    

# 1. HTML 태그 
## 1) 제목과 단락 요소 : heading, paragraph 

- 제목(heading) 태그?
  - 제목 태그는 문서 내 제목을 표현할 때 사용
  - "heading"을 줄여서 h로 쓰며, 제목의 레벨에 따라서 ```<h1>``` 에서 ```<h6>```까지 있음
  - 보통 ```<h1>```은 해당 페이지를 대표하는 큰 제목으로 주로 사용되며, 숫자가 올라갈수록 조금 더 낮은 수준의 소제목을 나타냄 
  - 하지만 현재 웹 페이지의 내용은 제목과 본문 식의 문서 형태보다는 주로 이미지나 그림처럼 시각적인 형태로 표현되고 있어서 제목 태그를 ```<h6>```까지 쓰는 경우는 거의 없음
  - 제목 태그를 사용하면, 일반 텍스트보다 더 강조되는 스타일이 적용되는데 이는 브라우저가 기본적으로 제목 태그에 제공하는 스타일	
- 단락(paragraph) 태그?
  - 단락 태그는 본문에 해당하는 내용인 paragraph를 줄여서 p로 씀
  - 화면에는 별다른 변화는 없지만, 이전보다 훨씬 의미에 맞게 잘 짜인 마크업 구조
- 개행
  - ```<p>```를 사용해서 단락으로 구분하면 자연스럽게 개행이 됨
  - 그럼 ```<p>``` 내부에서 임의로 개행을 하려면 : 개행하고자 하는 곳에서 ```<br>```을 선언
~~~
(예)
<h1>역사</h1>
<h2>개발</h2>
<p>
    1980년, 유럽 입자 물리 연구소(CERN)의 계약자였었던 물리학자 팀 버너스리가 HTML의 원형인 인콰이어를 제안하였다.
    ... 이하 생략
</p>
<h2>최초 규격</h2>
<p>
    HTML 최초의 일반 공개 설명은 1991년 말에 버너스리가 처음으로 인터넷에서 문서를 "HTML 태그"(HTML tag)로 부르면서 시작되었다.
    ... 이하 생략
</p>  
~~~
```--------------적용--------------```
<h1>역사</h1>
<h2>개발</h2>
<p>
    1980년, 유럽 입자 물리 연구소(CERN)의 계약자였었던 물리학자 팀 버너스리가 HTML의 원형인 인콰이어를 제안하였다.
    ... 이하 생략
</p>
<h2>최초 규격</h2>
<p>
    HTML 최초의 일반 공개 설명은 1991년 말에 버너스리가 처음으로 인터넷에서 문서를 "HTML 태그"(HTML tag)로 부르면서 시작되었다.
    ... 이하 생략
</p>
```--------------적용--------------```

## 2) 텍스트를 표현하는 태그/요소  

- 텍스트를 표현하는 태그/요소란?
  - 웹 표준화가 대두하면서, 웹 문서의 구조와 표현이 분리됨. 그 과정에서 많은 표현용 태그들이 사라졌고, 지금은 표현용 태그가 얼마 남지 않음
- bold 태그 ```<b>``` : 글자를 굵게 표현하는 태그
- italic 태그 ```<i>``` : 글자를 기울여서 표현하는 태그
  - HTML5 버전에서는 ```<i>``` 태그가 단순 표현용 태그에서 의미를 가지는 태그로 변경
  - 관용적 텍스트, 기술 용어, 분류 학적 명칭으로, 어떤 이유로 일반 텍스트에서 출발 된 텍스트의 범위를 나타냅니다. 역사적으로, 이들은  이 요소 의 이름 지정의 원래 소스인 이탤릭체를 사용하여 표시
- underline 태그 ```<u>``` : 글자의 밑줄을 표현하는 태그
- strike 태그 ```<s>``` : 태그는 글자의 중간선을 표현하는 태그
 - 예전에 존재했던 strike 태그와는 다른 태그로, strike 태그는 폐기되어 더는 사용할 수 없음

## 3) 앵커(anchor) 요소 [(더 많은 anchor 요소)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) 

- 앵커(anchor) 요소란?
  - HTML에서 HT(Hyper Text)는 링크를 의미하는 것으로, 링크는 클릭하기만 하면 다른 페이지로 쉽게 이동을 할 수 있음
- 앵커 태그 표현 : ```<a>```
  - a태그, 앵커, 링크 등 
~~~
(예) <a href="http://www.naver.com/" target="_blank">네이버</a>
~~~  
- href 속성 : 외부 링크 
  - href(hypertext reference). 링크 주소 입력 시 해당 버튼이 입력된 주소로 이동 
  - 형식 : ```<a href="(링크 목적지)">```
- href 속성 : 내부 링크 
  - ```<a>```를 통해 페이지 내부의 특정 요소로 초점을 이동할 수도 있는데, 이를 내부 링크라고 함 
  - 형식 : 내부 링크를 사용할 때는 href 속성값에 #을 쓰고 그 뒤에 페이지 내에서 이동하고자 하는 요소의 id 속성값을 적음
  - 주 용례 : 보통 페이지에 내용이 많아 스크롤이 길어질 경우, 빠르게 화면 최상단으로 이동하고자 할 때 내부 링크를 주로 사용. 웹페이지에서 화면 하단에 있는 'top' 또는 '맨 위로 이동하기' 버튼
~~~
(예) <a href="#some-element-id">회사 소개로 이동하기</a>

... 중략 ... 

<a href="some-element-id">회사 소개</a>
~~~
- href 속성 : mailto, tel
  - mailto : ```<a href="mailto:m.bluth@example.com">Email</a>```
  - tel : ```<a href="tel:+123456789">Phone</a>```    
- target 속성 
  - target 속성은 링크된 리소스를 어디에 표시할지를 나타내는 속성
  - 형식 : target="(target 속성값)" 
  - 크게 4가지 속성값이 있음
  - ```<a target="_self">``` : **현재 화면에 표시**한다는 의미로, target 속성이 선언되지 않으면 기본적으로 self와 같이 동작
  - ```<a target="_blank">``` : **새로운 창에 표시**한다는 의미로 외부 페이지가 나타나게끔 하는 속성
  - ```<a target="_parent">``` : 프레임이라는 특정 조건에서만 동작
  - ```<a target="_top">``` : 프레임이라는 특정 조건에서만 동작 

## 4) 의미가 없는 컨테이너 요소   

- 의미가 없는 컨테이너 요소란? 
  - 웹이 발전하면서 현재 웹페이지는 문서 형태보다는 시각적으로 정보를 표현하는 방향으로 많이 발전
  - HTML은 애초 문서를 위한 언어였기 때문에, 대부분의 태그들이 문서에 적합한 의미를 갖고 있음. 이런 태그들로는 현재의 다양한 콘텐츠를 표현하기에는 부족한 부분이 있음
  - 새로운 콘텐츠를 표현하기 위해 적합한 의미를 갖는 태그들이 생기기도 하는데, 콘텐츠를 표현하기에 적합한 태그가 없는 경우에는 주로 의미 없는 태그들을 사용
  - 이는 문서의 스타일이나 데이터 전송 등과 같은 부가적인 기능을 위해서도 종종 사용
  - 태그 자체에 아무 의미가 없으며, 단순히 요소들을 묶기 위해 사용되는 태그

- ```<div>``` 태그 
  - div(division) 태그는 **블록 레벨 태그**
  - 블록 레벨 요소는 기본적으로 한 줄을 생성해서 내용을 
  - 참고로, ```<p>``` 태그도 블록 레벨 태그
~~~
(예) 
<div class="warning">
    <img src="/media/examples/leopard.jpg"
         alt="An intimidating leopard.">
    <p>Beware of the leopard</p>
</div>
~~~ 
- ```<span>``` 태그
  - span 태그는 ***인라인 레벨 태그** 
  - 인라인 레벨 요소들은 블록 레벨 요소의 한 줄 안에서 표현되는 
  - 텍스트를 꾸며주는 ```<b>, <i>, <u>, <s>```는 모두 인라인 레벨 태그
~~~
(예) 
<p>Add the <span class="ingredient">basil</span>, <span class="ingredient">pine nuts</span> and <span class="ingredient">garlic</span> to a blender and blend into a paste.</p>

<p>Gradually add the <span class="ingredient">olive oil</span> while running the blender slowly.</p>
~~~
- (참고) 블록 레벨 요소
  - 기본적으로 블록 레벨 요소는 부모 요소의 전체 공간을 차지하여 "블록"을 만듬 
  - 브라우저는 보통 블록 레벨 요소의 앞과 뒤를 개행해서 그립니다. 상자를 쌓는 것 처럼 생각할 수 있음
- (참고) 인라인 요소
  - 인라인 요소는 콘텐츠의 흐름을 끊지 않고, 요소를 구성하는 태그에 할당된 공간만 차지 

## 5) 리스트 요소 

- ```<ul>``` 태그
  - ul(unordered list) 태그는 순서가 없는 리스트를 표현할 때 사용 
~~~
(예) 
<ul> 
    <li> 콩나물</li> 
    <li> 파</li> 
    <li> 국  간장</li> 
    ... 
</ul> 
~~~   

- ```<ol>``` 태그
  - ol(ordered list) 태그는 순서가 있는 리스트를 표현할 때 사용
  - 해당 태그를 선언한 후, 그 안에서 ```<li>```를 사용해 각 항목을 나타내서 사용
~~~
(예) 
<ol>
    <li>냄비에 국물용 멸치를 넣고 한소끔 끓여 멸치 육수를 7컵(1,400ml) 만든다.</li>
    <li>콩나물을 넣고 뚜껑을 덮어 콩나물이 익을 때까지 끓인다.</li>
    <li>뚜껑을 열고 대파, 마늘, 고춧가루를 넣고 끓인다.</li>
    ...
</ol> 
~~~
  - ```<ol>``` 태그의 type, start 속성
    - ```<ol>``` 태그는 기본적으로 숫자 1, 2, 3... 등 번호 붙임
    - 이 때, ```type``` 속성 사용하면 영문자, 숫자 등으로 순서 나타낼 수 있음 
      - ```type = "1" ``` : 숫자(기본값)
      - ```type = "a" ``` : 영문 소문자
      - ```type = "A" ``` : 영문 대문자
      - ```type = "i" ``` : 로마 숫자 소문자
      - ```type = "I" ``` : 로마 숫자 대문자    
    - 한편, 순서 목록은 기본적으로 "1"부터 시작하지만, ```start``` 속성 사용하면 시작 번호를 바꿀 수 있음 
~~~
(예) 
<ol type="a">
    <li>냄비에 국물용 멸치를 넣고 한소끔 끓여 멸치 육수를 7컵(1,400ml) 만든다.</li>
    <li>콩나물을 넣고 뚜껑을 덮어 콩나물이 익을 때까지 끓인다.</li>
    <li>뚜껑을 열고 대파, 마늘, 고춧가루를 넣고 끓인다.</li>
    ...
</ol>
<ol type="a" start="4">
    <li>냄비에 국물용 멸치를 넣고 한소끔 끓여 멸치 육수를 7컵(1,400ml) 만든다.</li>
    <li>콩나물을 넣고 뚜껑을 덮어 콩나물이 익을 때까지 끓인다.</li>
    <li>뚜껑을 열고 대파, 마늘, 고춧가루를 넣고 끓인다.</li>
    ...
</ol> 
~~~

- ```<dl>``` 태그 | [참고](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl)
  - dl(definition/description list) 태그, 즉 설명 목록 태그는 용어와 그에 대한 정의를 표현할 때 사용
  - ```<dt>``` : dt(definition title), 용어명을 나타내는 태그
  - ```<dd>``` : dd(definition description), 용어에 대한 정의 또는 설명을 나타내는 태그 
~~~
(예) 
<dl>
    <dt>리플리 증후군</dt>
    <dd>허구의 세계를 진실이라 믿고 거짓된 말과 행동을 상습적으로 반복하는 반사회적 성격장애를 뜻하는 용어</dd>
    <dt>피그말리온 효과</dt>
    <dd>타인의 기대나 관심으로 인하여 능률이 오르거나 결과가 좋아지는 현상</dd>
    <dt>언더독 효과</dt>
    <dd>사람들이 약자라고 믿는 주체를 응원하게 되는 현상</dd>
</dl> 
~~~

## 6) 이미지 요소 

- ```<img>``` 태그
  - img 태그는 문서에 이미지를 삽입하는 태그로, 닫는 태그가 없는 빈 태그 
  - ```<src>``` 속성
    - img 태그의 필수 속성으로, 이미지의 경로를 나타냄
    - ```<src="(이미지 경로)">```의 형태로 구성
  - ```<alt>``` 속성
    - 이미지의 대체 텍스트를 나타내는 속성 
~~~
(예) 
<img src="./images/pizza.png" alt="피자"> 
~~~
  - ```<width>```/```<height>``` 속성
    - 이미지의 가로/세로를 나타내는 속성 
    - 값을 입력하면 자동으로 픽셀(pixel) 단위로 계산
    - 해당 속성이 없으면 이미지 원본 크기로 노출되며, 둘 중 하나만 선언하면 나머지 한 속성은 선언한 속성의 크기에 맞춰 자동으로 비율에 맞게 변경 
~~~
(예) 
<img src="/examples/images/img_monalisa.png" alt="모나리자" height="280" width="180"> 
~~~ 
- 상대경로와 절대경로 
  - 상대경로
    - 현재 웹페이지를 기준으로 상대적인 이미지 위치를 나타냄
    - 해당 페이지의 디렉토리를 ```./```로 선언하고, 그 뒤의 경로를 입력  
  - 절대경로 : 실제 그 이미지가 위치한 곳의 전체 경로 
~~~
(예) 
<!-- 상대경로 -->
<img src="./images/pizza.png" alt="피자">

<!-- 절대경로 -->
<img src="C:/users/document/images/pizza.png" alt="피자">
<img src="http://www.naver.com/pizza.png" alt="피자">
~~~
- 주요 이미지 파일 형식별 특징 
  - gif : 제한적인 색을 사용하고, 용량이 적으며, 투명 이미지와 애니메이션 이미지를 지원하는 형식
  - jpg : 사진이나 일반적인 그림에 쓰이며, 높은 압축률과 자연스러운 색상 표현을 지원하는 형식. 투명을 지원하지 않음
  - png : 이미지 손실이 적으며, 투명과 반투명을 모두 지원하는 형식

## 7) 테이블 요소 

- 표의 구성 요소 
  - ```<table>``` 태그 
  - ```<th>``` 태그 : table header. header cell을 구성할 때 사용. ```<thead>``` 태그 내에서 사용
  - ```<tr>``` 태그 : table row. standard cell, 즉 일반 cell을 구성할 때 행(가로줄)을 만들 때 사용. 
  - ```<td>``` 태그 : table data. 실제 cell을 만드는 역할. 기본값은 굵은 글씨체에 중앙 정렬     
- 표의 구성 방식 
  - 좌상단에서 우측으로, 한 열이 지나면 아래 열로  
~~~
(예) 
<table>
    <tr>
        <td>1</td>
        <td>2</td>
        <td>3</td>
        <td>4</td>
    </tr>
    <tr>
        <td>5</td>
        <td>6</td>
        <td>7</td>
        <td>8</td>
    </tr>
    <tr>
        <td>9</td>
        <td>10</td>
        <td>11</td>
        <td>12</td>
    </tr>
    <tr>
        <td>13</td>
        <td>14</td>
        <td>15</td>
        <td>16</td>
    </tr>
</table>
~~~
  - css로 테두리 정의
~~~
(예) 
<!-- <head> 태그 내에서 정의 -->
<style>
  th, td { border: 1px solid; }
</style>
<!-- 또는 <th> 내부에서 정의 --> 
<thead>
  <tr>
      <th colspan="2">The table header</th>
  </tr>
</thead>
~~~
- 표의 구조와 관련된 태그 
  - ```<caption>``` : 표의 제목을 나타내는 태그
  - ```<thead>``` : 제목 행을 그룹화하는 태그
  - ```<tfoot>``` : 바닥 행을 그룹화하는 태그
  - ```<tbody>``` : 본문 행을 그룹화하는 태그
~~~
(예) 
<table> 
    <caption>Monthly Savings</caption>
    <thead>
        <tr>
            <th>Month</th>
             <th>Savings</th>
        </tr>
    </thead>
    <tbody>
        <tr>
             <td>January</td>
            <td>$100</td>
        </tr>
        <tr>
             <td>February</td>
            <td>$80</td>
        </tr> 
    </tbody>
    <tfoot>
        <tr>
             <td>Sum</td>
            <td>$180</td>
        </tr>
    </tfoot>
 </table>
~~~
- ```<table>``` 태그의 주요 속성 (모든 속성은 {속성}="(숫자)" 형태로 구성) 
  - ```colspan 속성``` : column span. 셀 가로줄을 합치는 개수를 지정. row의 개수는 tr 하위에 설정된 td의 총 개수. 이 중 colspan을 통해 td 중 합치고자 하는 개수를 숫자로 입력. 
~~~
(예) 
<table border="1">
  <tr>
    <td colspan="2">병아리반</td> <!--td 개수 2개 입력해야 하는데, colspan으로 td 열 개수를 직접 입력함-->
  </tr>
  <tr>
    <td> 1</td>
    <td>김영희</td>
  </tr>
  <tr>
    <td> 2</td>
    <td>김순자</td>
  </tr>
</table>
~~~
  - ```rowspan 속성``` : row span. 셀 세로줄을 합치는 개수를 지정. row 개수 중 합치고자 하는 행 개수를 입력
~~~
(예) 
<table border="1" >
  <tr>
    <td rowspan="3">병아리반</td> <!--tr 개수가 총 3개이므로, 3 입력하므로써 열을 한번에 합침-->
    <td>김순자</td>
  </tr>
  <tr>
    <td>김영희</td>
  </tr>
  <tr>
    <td>이철수</td>
  </tr>
</table>
~~~ 
  - ```border``` 속성 : 테이블 경계선 굵기 지정 
  - ```width``` 속성 : 너비 지정. pixel 또는 %로 
  - ```height``` 속성 : 높이 지정. pixel 또는 %로
  - ```cellpadding``` 속성 : 셀과 경계선 사이 여백 
  - ```cellspacing``` 속성 : 셀과 셀 사이의 여백 
  - ```align``` 속성 : 셀 가로줄(tr)의 데이터 정렬을 right, center, left 중 하나로 지정
  - ```valign``` 속성 : 셀 세로줄의 데이터 정렬을 top, middle, bottom 중 하나로 지정 
  - ```bgcolor``` 속성 : 배경색 설정. 색상 이름(예 : green)이나 색상코드(예 : #000000) 등으로 지정 
  - ```boldercolor``` 속성 : 경계선 색상 설정. 색상 이름(예 : green)이나 색상코드(예 : #000000) 등으로 지정
- ```<colgroup>``` 태그와 ```<col>``` 태그
  - 테이블의 컬럼(```<td>``` 태그)에 적용할 스타일 width와 bakcground를 해당 태그에서 미리 적용할 수 있게 하여 열을 묶어주는 태그
  - 특히 각 컬럼의 길이를 설정하는데 가장 많이 쓰임
  - ```<col>``` 태그는 열 1개, ```<colgroup>``` 태그는 2개 이상의 열을 묶어 지정할 때 사용
  - 이 때, ```<col>``` 태그는 닫는 태그가 없음
  - 위 2개 태그는 반드시 ```<caption>``` 태그 뒤에 써야 함. 즉, 표 내용이 시작하기 전에 열의 상태를 알려줌.       
~~~
(기본형)
<caption>(blabla)</caption>
<colgroup>
  <col>  
</colgroup>
~~~ 
  - 그리고 ```<col>``` 태그를 사용할 때에는 ```<colgroup>``` 태그 안에 ```<col>``` 태그를 포함해 표 전체 열 개수만큼 ```<col>``` 태그를 넣어야 함. 즉, 스타일 속성 지정하지 않은 열이 있을 경우 각각 ```<col>``` 태그를 작성해야 함
~~~
(예) 
<table border="1">
  <caption>선물용과 가정용 상품 구성</caption>
  <colgroup>
    <col width="50px" style="background: red" /> <!-- 첫 번째 열 배경색 지정--> 
    <col> <!-- 스타일 없어도 <col> 명시 --> 
    <col width="100px" style="background: green" />
    <col width="100px" style="background: green" /> 
    <!-- 위 내용은 <col span="2" style="background: green" /> 이렇게도 쓸 수 있음 --> 
  </colgroup>

  <thead>
    <tr>
      <td>번호</td>
      <td>제목</td>
      <td>이름</td>
      <td>내용</td>
    </tr>
  </thead>
</table>
~~~
  - ```scope 속성```
    - ```<th>``` 태그의 scope 속성은 해당 헤더 셀이 관련되는 셀의 종류를 명시함
    - 일반 웹 브라우저에서는 ```<th>``` 요소에 scope 속성을 명시해도 아무런 시각적 효과도 나타나지 않지만, 스크린 리더기와 같은 장치에서는 유용하게 사용될 수 있음
    - ```scope 속성```은 ```scope=(속성값)``` 형태로 구성  
      - col 속성값 : 해당 셀이 열(column)을 위한 헤더 셀임을 명시
      - row 속성값 : 해당 셀이 행(row)을 위한 헤더 셀임을 명시
      - colgroup 속성값 : 해당 셀이 열의 그룹을 위한 헤더 셀임을 명시
      - rowgroup 속성값 : 해당 셀이 행의 그룹을 위한 헤더 셀임을 명시
~~~
(예) 
<table width="100%" summary="월별 스마트폰, 테블리PC, 데스트탑PC 판매현황">
  <caption>상품에 따른 월별 판매현황</caption>
    <colgroup>
      <col width="20%" />
      <col width="25%" />
      <col width="25%" />
      <col width="30%" />
    </colgroup>
   <thead>
    <tr>
      <th rowspan="2" scope="col">구분</th>
      <th colspan= "3" scope="colgroup">상품종류</th>
      <!-- ← scope="colgroup" 행으로 병합되었때는 그룹으로 사용-->
    </tr>
    <tr>
      <th scope="col">스마트폰</th>
      <th scope="col">테블리PC</th>
       <th scope="col">데스크탑PC</th>
     </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">1월</th>
          <td>5만대</th>
          <td>3만대</th>
          <td>1만대</th>
       </tr>
       <tr>
         <th scope="row">2월</th>
           <td>7만대</th>
           <td>2만대</th>
           <td>1만대</th>
         </tr>
     </tbody>
    </table>
~~~
  - header 속성  































