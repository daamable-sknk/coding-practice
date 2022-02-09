> 기본 강의 구성 
> > [부스트코스](https://www.boostcourse.org/)의 [비전공자를 위한 HTML/CSS](https://www.boostcourse.org/cs120)
> 참고 자료
> > 개발자를 위한 웹 기술 : [HTML: Hypertext Markup Language](https://developer.mozilla.org/ko/docs/Web/HTML)    

# 1. 글꼴 관련 스타일  

## 1) font-family 속성   

- 글꼴 지정을 위해서 font-family 속성을 사용 
  - 웹 문서 텍스트는 사용자 시스템 글꼴을 이용해 웹 브라우저 화면에 표시 
~~~
(기본형)
font-family:<글꼴 이름> | [<글꼴 이름>, <글꼴 이름>]
~~~ 







- 스타일 형식 기본 구조 
~~~
(기본형)
선택자 { 속성1: 속성값; 속성2: 속성값2; }
~~~ 
  - 선택자(selector) : 스타일을 어떤 태그에 적용할 지 알려줌 
    - 중괄호 ```({})```에 속성 표현
  - 스타일 규칙 : ```속성(property)```과 ```속성값(value)```을 하나의 쌍으로 구성
    - ```세미콜론```으로 구분하여 여러 개의 스타일 규칙 지정 가능
    - 여러 개의 스타일은 한 줄 또는 여러 줄로 표현 모두 가능 
  - 스타일 주석 표기 
    - ```/*```와 ```*/``` 사이에 내용 입력
    - CSS의 코드 크기가 작을수록 네트워크를 통한 파일 다운 유리하므로, 배포 시 주석, 줄바꿈 문자 등은 삭제하여 경량화(참고 : [CSS minifier](https://www.toptal.com/developers/cssminifier/))    

- CSS(Cascading Style Sheet)?
  - HTML(마크업 언어)을 꾸며주는 표현용 언어 
  - HTML로 문서의 정보와 구조 설계, CSS로 웹 문서의 디자인을 구성
- HTML+CSS 사용 이유 
  - 문서와 디자인을 구분하여 상호간의 개발을 보다 효율적으로 구성할 수 있음 
