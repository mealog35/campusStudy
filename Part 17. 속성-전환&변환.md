# Part 17. 속성-전환&변환

### 전환(transitions)
  - css 속성의 전환 효과를 지정
  - transition-property : 전환 효과를 사용할 속성 이름을 설정
  - transition-timing-function : linear(일정한 속도) 속도를 느리게 할건지 아니면 빠르게 할건지를 나타내는 함수
  - transition-delay : 전환 효과가 몇 초뒤에 시작할지 / transition: 2s(전환시간) 3s(delay)

### transform
  - 요소의 변환 효과를 지정 (2d 3d)
  - rotate(90deg) : 90도 회전
  - translate(30px,30px) : x,y축을 변경해서 이동시키겠다는 의미
  - scale(1.5) : 크기를 1.5배로 크게 하겠다
  - skew(45deg) : 비틀어버린다는 의미
  - perspective(100px) : 원근감을 나타냄 / 속성을 나타냄
  - transform-origin : 변환시키기 위한 기준점 
  - transform-style : preserve-3d 자식요소가 3d를 사용할 수 있도록 하겠다는 의미

### perspective
  - 하위 요소를 관찰하는 원근거리를 설정
    - perspective : 관찰 대상의 부모 요소에 적용
    - transform : perspective() : 관찰 대상에 직접 적용함
    - perspective-origin : 원근 거리의 기준점을 설정
    - backface-visibility : 3d 변환으로 회전된 요소의 뒷면 숨김을 설정 (hidden:숨김)

### matrix(a,b,c,d,e,f)
  - 요소의 2차원 변환 효과를 지정 scale(),skew(),translate(),rotate() 이거를 동시에 아우르고 있음
  - 이거를 동시에 계산하는것에는 어려운 점
