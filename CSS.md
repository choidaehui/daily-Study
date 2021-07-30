## CSS 태그 정리 

      1. 선택자
          selector { 
               property: value;
          }

          padding -> 컨테츠 내부 공간에 적용
          margin -> 컨텐츠 외부 공간에 적용
          border -> 컨텐츠 경계선에 적용

          예) 
          .red {
            width: 100px;
            height: 100px;
            padding: 20px 0px; -> 위, 아래 20px padding값 적용
                 -> 왼쪽, 오른쪽 0px padding값 적용
            padding: 20px 20px 20px 20px; -> 위, 오른쪽, 아래, 왼쪽 순서로 padding값 적용
            border: 2px dashed red;
          }

      참고 사이트 -> CSS reference

    2. display, position의 사용법

        ㄱ. display
        예)
        div {
          background: red;
          display: inline; -> 컨텐츠 크기에 따라 변경되는 아이템을 배치
                    inline-block; -> 한 줄에 여러개 컨텐츠가 배치되는 상자
                    block; -> 한 줄에 하나씩 배치되는 상자				
        }

        ㄴ. position-> 기본값 static 
          position: relative; -> 원래 있던 자리에서 상대적으로 위치 변경
          position: absolute; -> 아이템이 담겨있는 상위 상자 안에서 위치 변경 
          position: sticky; -> 스크롤 해도 원래 있던 자리에 그대로 위치 
          position: fixed; -> 웹사이트 페이지에서 위치 변경

    3. Flex box

        참고 사이트 -> a complete guide to flexbox 사이트
                 Flex box froggy 실습 사이트

        ㄱ. float -> 이미지와 텍스트를 혼합해서 사용할 때 구분해 줌
          float: left; -> 이미지가 왼편에 배치
          float: right; -> 이미지가 오른편에 배치 
          float: center; -> 이미지가 중앙에 배치

        ㄴ. 컨테이너에 사용되는 Flex box 태그들
          display: flex;
          flex-direction: row; -> 수평축 중심
                  column; -> 수직축 중심
          flex-wrap: nowrap; -> 기본값
             wrap; -> 아이템이 디스플레이에 따라 줄 바꿈
          flex-flow: column nowrap; -> flex-direction, flex-wrap 결합

          justify-content: flex-start;
                    flex-end; -> 아이템의 순서는 고정
                    space-around;
                    space-evenly;
                    space-between; -> 똑같은 공간을 두고 아이템 들을 배치
          -> 중심 축에서 아이템 배치

          align-items: baseline; -> 텍스트가 균등하게 배치
          align-content: justify-content 속성 값 그대로 사용 
          -> 반대 축에서 아이템 배치

        ㄷ. 아이템에서 사용되는 Flex box 태그들
          order: 0; -> 기본값
          flex-grow: 0; -> 기본값 
             1; -> 아이템이 컨테이너를 채움
             2; -> 다른 아이템 보다 2배 크기로 컨테이너를 채움
          flex-shrink: 0; -> 기본값
              1; -> 아이템이 컨테이너를 채움
              2; -> 다른 아이템 보다 2배 크기로 컨테이너에서 줄어듬
          flex-basis: auto; -> 기본값
             60%; -> 아이템이 컨테이너 크기의 60%를 차지
          align-self: center; -> 아이템 하나만 위치를 변경
        예)
        .container {
          height: 80vh; -> 웹페이지 view의 높이 80% 사용
        }

        참고 사이트 -> color tool 사이트(material.io) -> 색 정할 때 사용
                           MDN 사이트 -> using media queries  페이지 -> 반응형 웹사이트 궁금할 때

    4. 반응형 유닛

        참고 사이트 -> px to em.com -> 픽셀을 em값으로 변경할 때 사용

        ㄱ. 절대적인 유닛
        px(픽셀) -> 컨테이너 사이즈가 변경되어도 아이템 크기는 그대로 유지
        80%(퍼센트) -> 부모 아이템 크기의 80%를 사용

        ㄴ. 상대적인 유닛
        em(16px == 1em)  -> 선택된 폰트 사이즈와 관계 없이 크기가 고정 
            -> 부모의 폰트 사이즈를 상대적으로 곱한 값
        rem(r -> root) -> 루트 요소에서 상대적으로 폰트 사이즈 결정
        vw -> 예) 100vw -> 브라우저 넓이의 100% 사용
        vh -> 예) 50vh -> 브라우저 높이의 50% 사용
        % -> em 대신 사용 가능
           -> 부모 요소에서 상대적으로 크기 결정

        예)
        .contents {
          font-size: 1rem; -> 웹 사이트에 폰트 크기 고정
          padding: 0.5em 0.5rem; -> padding값으로 주로 사용
                    padding: 1em; -> 디스플레이를 넓히거나 줄일 때 폰트 크기 변경에 따라 padding 값도 변경
        }   

        @media screen and (max width: 48rem) {
                     -> 더 유동적인 반응형 웹 사이트 구현 가능
        }