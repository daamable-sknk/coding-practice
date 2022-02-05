> 기본 강의 구성 
> > [부스트코스](https://www.boostcourse.org/)의 [비전공자를 위한 HTML/CSS](https://www.boostcourse.org/cs120)
> 참고 자료
> > 개발자를 위한 웹 기술 : [HTML: Hypertext Markup Language](https://developer.mozilla.org/ko/docs/Web/HTML)    

# 1. CSS란? 

## 1) 웹 문서(HTML)와 디자인(CSS)의 분리  

- CSS(Cascading Style Sheet)?
  - HTML(마크업 언어)을 꾸며주는 표현용 언어 
  - HTML로 문서의 정보와 구조 설계, CSS로 웹 문서의 디자인을 구성
- HTML+CSS 사용 이유 
  - 문서와 디자인을 구분하여 상호간의 개발을 보다 효율적으로 구성할 수 있음 

## 2) 스타일과 스타일 시트 

- 스타일 형식 기본 구조 
~~~
(기본형)
선택자 { 속성1: 속성값; 속성2: 속성값2; }
~~~ 
  - 선택자 : 스타일을 어떤 태그에 적용할 지 알려줌 
    - 중괄호 ```({})```에 속성 표현
  - 스타일 규칙 : ```속성```과 ```속성값```을 하나의 쌍으로 구성
    - ```세미콜론```으로 구분하여 여러 개의 스타일 규칙 지정 가능
    - 여러 개의 스타일은 한 줄 또는 여러 줄로 표현 모두 가능 
  - 스타일 주석 표기 
    - ```/*```와 ```*/``` 사이에 내용 입력
    - CSS의 코드 크기가 작을수록 네트워크를 통한 파일 다운 유리하므로, 배포 시 주석, 줄바꿈 문자 등은 삭제하여 경량화(참고 : [CSS minifier](https://www.toptal.com/developers/cssminifier/))    
~~~
(예 : <p> 태그에 스타일 적용)
/* 주석을 
여러줄로 입력 */
p {
  text-align: center; /* 주석을 한 줄에 입력 */ 
  color: blue;
}
~~~ 

- 스타일 시트 문서 구성하기 
  - <b>브라우저 기본 스타일</b> : 웹 브라우저에 기본으로 만들어져 있는 스타일 시트 
  - <b>사용자 스타일</b> : 사용자가 직접 만든 스타일 시트  
    - <b>인라인 스타일 시</b> : 간단한 스타일 정보를 HTML 태그 내 직접 입력하는 방식
    - <b>내부 스타일 시트</b>
      - 단일한 웹 문서 안에 사용할 스타일을 같은 문서 내에 정의한 것
      - ```<head>``` 태그 안 ```<style>``` 태그 사이에 작성 
    - <b>외부 스타일 시트</b> 
      - 스타일 정보를 문서 외부에 따로 저장하여 관리 
      - 문서의 디자인 스타일 일관성, 코드 경량화 등을 고려하여, 여러 문서에 적용될 스타일을 별도 파일로 저장해두고 필요할 때 가져와서 사용 
      - 이 때 저장한 스타일 정보 파일을 ```스타일 시트```라고 하고, ```.css``` 파일 확장자 사용  
      - 외부 스타일 시트 파일 사용 시에는 ```<style>```태그 대신 ```<link>``` 태그 사용
      - ```<link>``` 태그 기본형 : ```<link rel="stylesheet" type="text/css" href="외부 스타일 시트 파일 경로">```     
~~~
(인라인 스타일 예시)
<h1 style="color: red;">스타일 시트</h1>
<p style="color: blue;">스타일 시트 본문</p>
~~~ 

~~~
(내부 스타일 예시)
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style> <!-- 인라인 스타일 작성 -->
            h1 {
                padding: 10px;
                background-color: #000;
                color: #fff;
            }
        </style>
    </head>
    <body>
        <header>
            <div>로고 위치 입니다</div>
        </header>
    
        <main>
            <h1>내부 스타일 시트</h1> <!-- 인라인으로 작성한 스타일이 적용되는 태 -->
            <article>아티클1</article>
            <article>아티클2</article>
            <article>
                아티클3
                <section>섹션1</section>
                <section>섹션2</section>
            </article>
        </main>
        
        <footer>
            <div>COPYRIGHT c 2021 누구누구</div>
        </footer>
    </body>
</html>
~~~

~~~
(외부 스타일 시트 예시)
<!-- style.css 파일에 다음과 같은 스타일을 정의해둠 --> 
h1 {
    padding: 10px;
    background-color: #000;
    color: #fff;
}

<!-- 실제 HTML 문서에서는 다음과 같이 활용 --> 
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <link rel="stylesheet" type="text/css" href="./css/style.css"> <!-- <head> 태그 내에 <link> 태그를 기술하고, 연결될 css 파일을 href로 설정함 -->
    </head>
    <body>
        <header>
            <div>로고 위치 입니다</div>
        </header>
        <main>
            <h1>외부 스타일 시트</h1>
            <article>아티클1</article>
            <article>아티클2</article>
            <article>
                아티클3
                <section>섹션1</section>
                <section>섹션2</section>
            </article>
        </main>
        <footer>
            <div>COPYRIGHT c 2021 누구누구</div>
        </footer>
    </body>
</html>
~~~ 

## 3) CSS 기본 선택자 

- 전체 선택자(universal selector) 
  - 스타일을 문서 모든 요소에, 주로 모든 하위 요소에 스타일을 한꺼번에 적용할 때 사용 
  - 전체 선택자를 사용할 때는 특정 선택자 대신 ```*(별표)``` 사용 
~~~
(전체 선택자 기본형)
* { 속성: 값; }
~~~ 

- 타입 선택자(type selector) 
  - 특정 태그를 사용한 모든 요소에 스타일 적용 
~~~
(타입 선택자 기본형)
태그명 { 속성: 값; }
~~~ 

- 클래스 선택자(class selector)
  - 같은 태그라도 특정 부분만 선택하여 따로 스타일을 적용할 때 사용 
  - 클래스 이름을 사용하여 다른 선택자와 구별하는 데, 이 때 클래스 이름 앞에 ```마침표(.)```를 붙여야 함 
  - 클래스 이름은 구별하기 쉽게 임의 지정
~~~
(클래스 선택자 기본형)
.클래스명 { 속성: 값; }
~~~ 
  - 클래스 선택자 사용해 만든 스타일을 클래스 스타일이라고 하며, 이미 만든 클래스 스타일을 적용할 때는 태그 안에 ```class="클래스명"``` 등 클래스 속성을 사용 
~~~
(클래스 선택자 적용 예시)
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style> <!-- bg 클래스 스타일 정의 -->
            .bg { 
                padding: 10px;
                background-color: #000;
                color: #fff;
            }
            .accent {
              border: 1px;
            }
        </style>
    </head>
    <body>
        <header>
            <div>로고 위치 입니다</div>
        </header>
    
        <main>
            <h1 class="bg accent">내부 스타일 시트</h1> <!-- 클래스 스타일이 적용되는 태그. 이 때 두 개 이상의 클래스 스타일 적용할 경우, class 태그에 클래스명을 공백으로 구분하여 기재 -->
            <article>아티클1</article>
            <article>아티클2</article>
            <article>
                아티클3
                <section>섹션1</section>
                <section>섹션2</section>
            </article>
        </main>
        
        <footer>
            <div>COPYRIGHT c 2021 누구누구</div>
        </footer>
    </body>
</html>
~~~

- ID 선택자(ID selector) 
  - 클래스 선택자처럼 웹 문서의 특정 부분을 선택하여 스타일 지정할 때 사용
  - 단, ```마침표(.)``` 대신 ```#``` 사용
  - ID 스타일 적용 시 ```id="ID명"``` 사용
  - 클래스 선택자 vs ID 선택자 
    - 문서에서 여러 번 적용 가능 vs 문서에서 한 번만 적용 가능 
  - 따라서, 문서의 고유한 스타일, 즉 레이아웃 관련 스타일을 지정하거나, 웹 요소에 Javascript 사용하면서 요소 구분 시 사용  

~~~
(ID 선택자 기본형)
.ID명 { 속성: 값; }
~~~ 

~~~
(ID 선택자 예시)
<!-- (생략) -->
<style>
    #container {
        width: 500px;
        margin: 10px auto;
        padding: 10px auto;
        border: 1px solid #000; 
    }
</style>
<!-- (생략) -->
<div id="container">
    <h1>제목</h1>
</div> 

<!-- (생략) -->
~~~ 

- 그룹 선택자
  - 여러 선택자에 동일한 스타일 규칙이 있을 경우, 쉼표(,)를 활용해 여러 선택자를 나열한 후, 스타일 규칙을 한 번만 정의 가능 
~~~
(그룹 선택자 예시)
<!-- 서로 다른 선택자에 동일한 스타일이 있을 경우 --> 
h1 {
    text-align: center;
}

p {
    text-align: center;
}

<!-- 다음 처럼 재구성 가능 --> 
h1, p {
    text-align: center;
}
~~~ 

## 4) 캐스케이딩 스타일 시트 알아보기 
- 캐스케이딩(cascading)의 의미 
  - "Cascading"이란 우선순위가 폭포수처럼 위에서 아래로, 계단식으로 적용된다는 의미
  - 스타일의 충돌을 막기 위한 2가지 방법 
    - 스타일 우선 순위 : 스타일 규칙의 중요도와 적용 범위에 따라 우선순위 결정 
    - 스타일 상속 : 태그의 포함 관계에 따라 부모 요소의 스타일을 자식 요소로 결정 
- 스타일 우선 순위 
  - 스타일에 따른 우선 순위 
    - 1) 사용자(user) 스타일 : 컴퓨터 사용자가 지정한 스타일 
    - 2) 제작자(author) 스타일 : 웹 문서 제작자가 지정한 스타일 
    - 3) 브라우저(browser) 기본 스타일 : 브라우저에서 정의한 스타일 
  - 선택자 정의에 따른 우선 순위 
    - 1) ```!important``` : 어떤 스타일보다 우선 적용 
    - 2) 인라인 스타일 : 태그 안에 ```style``` 속성을 사용해 해당 태그에만 스타일 적용
    - 3) ID 스타일  
    - 4) 클래스 스타일 
    - 5) 타입 스타일  
  - 코드 작성 순서에 따른 우선 순위 
    - 나중에 작성한 스타일에 먼저 작성한 스타일을 덮어씀 
~~~
(예)
<!-- (생략) --> 
<style>
    p {
        color: black;
    }
    h1 {
        color: brown !important; 
    }
    p {
        color: blue;
    }
</style>
<!-- (생략) -->
<h1 style="color:green">제목</h1> <!-- 인라인 스타일이 있지만, 타입 스타일에 !important가 있으므로 brown으로 표현 -->  
<p style="color:red;">내용 작성1</p> <!-- 타입 스타일보다 인라인 스타일이 우선하므로, red로 표현 -->  
<p>내용 작성2</p> <!--타입 스타일 중 보다 아래(나중)에 있는 blue로 표현 -->

<!-- (생략) -->
~~~ 

  - 스타일 상속 
    - 기본 개념 : 자식 요소에서 별도 스타일을 지정하지 않으면 부모 요소 스타일이 자식 요소에 전달
      - 예를 들어, ```<body>``` 태그는 웹 문서의 모든 태그의 부모 요소임. 따라서 해당 태그에 스타일을 정의하면, 그 스타일은 웹 문서 모든 태그에 (우선 순위가 없는 한) 광역으로 적용



























