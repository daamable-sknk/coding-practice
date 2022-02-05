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
  - 스타일 시트 
    - <b>브라우저 기본 스타일</b> : 웹 브라우저에 기본으로 만들어져 있는 스타일 시트 
    - <b>사용자 스타일</b> : 사용자가 직접 만든 스타일 시트  
      - <b>인라인 스타일</b> : 간단한 스타일 정보를 HTML 태그 내 직접 입력하는 방식 
~~~
(인라인 스타일 예시)
<h1 style="color: red;">스타일 시트</h1>
<p style="color: blue;">스타일 시트 본문</p>
~~~ 
      - <b>내부 스타일 시트</b>
        - 단일한 웹 문서 안에 사용할 스타일을 같은 문서 내에 정의한 것
        - ```<head>``` 태그 안 ```<style>``` 태그 사이에 작성 
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
      - <b>외부 스타일 시트</b> 
        - 스타일 정보를 문서 외부에 따로 저장하여 관리 
        - 문서의 디자인 스타일 일관성, 코드 경량화 등을 고려하여, 여러 문서에 적용될 스타일을 별도 파일로 저장해두고 필요할 때 가져와서 사용 
        - 이 때 저장한 스타일 정보 파일을 ```스타일 시트```라고 하고, ```.css``` 파일 확장자 사용  
        - 외부 스타일 시트 파일 사용 시에는 ```<style>```태그 대신 ```<link>``` 태그 사용 
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
(기본형)
* { 속성: 값; }
~~~ 

- 타입 선택자(type selector) 
  - 특정 태그를 사용한 모든 요소에 스타일 적용 
~~~
(기본형)
태그명 { 속성: 값; }
~~~ 

- 클래스 선택자(class selector)
  - 같은 태그라도 특정 부분만 선택하여 따로 스타일을 적용할 때 사용 
  - 클래스 이름을 사용하여 다른 선택자와 구별하는 데, 이 때 클래스 이름 앞에 ```마침표(.)```를 붙여야 함 
  - 클래스 이름은 구별하기 쉽게 임의 지정
~~~
(기본형)
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

- ID 선택자 
- 그룹 선택자 
- 



```<p>```
~~~
(예)
~~~ 


























