## kokoa-clone

- <html lang="kr">
  * html에 사용하는 언어를 설정할 수 있다
  * body 
    - display: block
- <head> 안에서
  - <title>브라우저 탭의 제목을 설정한다</title>
  - <Link rel="shortcut icon" sizes="16x16 32x32 64x64" href="이미"/>
    * 브라우저 탭에서 이미지가 삽입이된다
  - <meta name="description" content="내용"/> 
    * 검색할 경우 웹사이트의 설명을 표시할 수 있다
  - <meta charset="utf-8"/> 
    * 문자를 설정해준다
  - <meta property="og:site_name" content="사이트 이름을 설정" />
    * og 카카오톡등 SNS로 공유할경우 속성
    * og:type, og:url, og:imgae, og:description, og:local, og:image:width, og:image:height 등등
- <div> 태그 block이라서 같은 라인에 태그가 올수없다

* Box형태: <div>

  - margin
    - box의 border(경계)의 바깥에 있는 공간이다
    - 20px 10px 5px 0px (상, 우, 하, 좌)
    - 20px 10px (상하, 좌우)
  - padding
  - border: 경계선 굵기(px), 선종류, 선컬러
    - solid, dot
  - display
    - 속성으로 inline, block로 변경가능하다
    - inline 같은 라인에 정렬하기위한 속성
    - 높이와 너비가 적용되지않는다 \*box가 아니다
    - block
      - block은 높이와 너비가 있다
    - flex: 두가지 축을가지고 있으며 그것을 이용하여 정렬한다
      - justify-content: 수평기준으로 정렬
        - center: 중앙정렬
        - space-evenly, space-around, space-between
          - 빈공간을 같은 크기로 나누어서 배치 된다
      - align-items: 수직기준으로 정렬
        - 속성값 center: 부모태그의 height기준으로 중앙정렬한다
        - 속성값 stretch: 부모태그의 height만큼 자식태그를 늘린다
      - flex-direction: display: flex의 default값은 row이다
        - 속성값 column: 수평정렬되는 태그들을 수직정렬로
        - 속성값 colum: column-recer 순서가 위아래로 바뀐다
      - flex-wrap:
        - 속성값 wrap: 브라우저가 좁아질 경우 태그의 영역이 유지되며 영역보다 좁아지면 다음라인으로 내려가게된다
        - 속성값 nowrap: 태그 자체의 영역이 줄어들어 같은라인을 유지
  - position: 기본적으로 top, left, right, bottom을 이용하여 개별적으로 이동하는데 그 기준을 어디서 부터 이동하는지를 기준을 설정한다
    - 속성의 값 static:
    - 속성의 값 fixed: 스크롤로 브라우저 위치가 변경되어도 항상 위치가 유지되어있다
      - top, left, right, bottom으로 위치를 변경한다면 기존의 레이아웃와 겹치게되는 현상이 발생한다
    - 속성의 값 relative: top, left, right, bottom을 변경하면 현재 위치에서 개별적인 위치 변경이 가능하다 예) top -10px
    - 속성의 값 absolute: position이 relative로 설정된 부모태그의 영역 안에서 이동하게된다

* state

  - active: 클릭시 변경이 가능한 스타일링
  - hover: 마우스를 지정된 영역에 근접하면 변경이 가능한 스타일링
  - focus: input 태그에서 영역을 잡게되면 변경이 가능한 스타일링
  - visited: a태그를 클릭해서 어떠한 사이트에 방문하게되면 변경이 가능한 스타일링
  - focus-whthin: 자식태그가 접근되면 부모태그 스타일링 가능
  - 코드 작성 예) button:active, input:focus, 이중사용 가능(form: hover, input:focus)

  * 태그::placeholder, ::selection

* transition

  - transition은 hover, active등의 변화하는 애니매이션이 어떻게 변할지 말해주는것이다
    그러므로 hover로 변경되는 스타일값을 정해주고 변경되는 태그에 transition을 지정해주어야한다

  - 코드작성 예) transition: backgound-color 10s ease-in-out, color 5s ease-in-out; transition: all 5s ease-in-out

  - ease, ease-in, ease-in-out, ease-out linear (애니매이션을 변경하는 속도를 제어한다)

* transform

  - 속성 값: rotateZ(10deg), scale(2, 2), translateX(-50px), skewY(45deg)
  - hover 같은 state 기능으로 동적인 변경이 가능하다
  - 구글 검색 transform mdn

* animation: css animation 구글 검색

- @keyframe
  - @keyframe superConfigFlip { from { transform: rotateY(0) }, to { transform: rotateY(360deg) } }
    - from, to 대신 0%, 50%, 100%로 계속적인 애니매이션이 작동된다 (%는 더욱 잘게 쪼겔수 있다)
  - 위와같이 <style></style>에 선언하고 애니매이션을 적용할 태그에 animation: superConfigFlip 5s ease-in-out infinite속성을 선언한다 (infinite는 무한반복이된다)
  - 랜더링할 경우 superConfigFlip를 불러와 state 기능을 하지않아도 애니매이션이 실행된다

* media width 따른 스타일변경: min-device-width 구글 검색, css media queries mdn 구글 검색

  - @media screen and (min-width: 601px) and (max-width: 1200px) { 현재 브라우저에 따른 스타일변경
    div {
    background-color: wheat;
    }
    }
    @media screen and (orientation: landscape) { orientation: landscape가로 일경우 스타일 변경
    span {
    display: none;
    }
    }

* 실무 HTML, CSS 적용
  - block을 가진 태그속성을 같은 라인에 적용하는방법
    - 부모태그를 만들어서 CSS의 display속성을 flex 적용한다
    - 또 한가지는 CSS의 justify-content속성을 center 적용한다
    - 자식태그들이 같은라인으로 적용이된다
    * 예제>
      부모태그 {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      }
  - height: 100vh
    - viewport height를 현재 브라우저의 전체높이를 말한다
  - opacity
    - 색의 채도를 낮춘다 0.1 ~ 1
