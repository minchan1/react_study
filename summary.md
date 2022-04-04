

# 0403

- 암기할 필요 없다. 이해하기
  리액트를 import했기 때문에 createElement function을 가진 리액트 object에 접근 가능
  const span 그러나 createElement(“span”) 은 반드시 생성하고자 하는 HTML 태그와 똑같아야함

  React JS - 어플리케이션이 아주 인터랙티브하도록 만들어주는 library. 엔진과 같다.
  React-dom - library 또는 package. 모든 react element들을 HTML body에 둘 수 있도록 해줌.
  ReactDOM.render() - render의 의미는 react element를 가지고 HTML로 만들어 배치한다는 것. 즉, 사용자에게 보여준다는 의미
  ReactDOM.render(span, span이 가야할 위치)
  -> 그래서 보통 body에 id=“root” 만들어서 span을 root 안에 두라고 함

  React.createElement("span", {span의 property}, “span의 내용”)
  -> property는 class name, id도 가능 style도 가능
  -> 참고만 하고 외우지 말기. 이렇게 쓸 일 없음

  바닐라JS는 HTML -> JS 순서
  리액트는 JS -> HTML 순서

  JS가 element를 생성하고 React JS가 그것을 HTML로 번역하는 것
  React JS는 업데이트 해야 하는 HTML을 업데이트 할 수 있음





# 0404

- state를 세팅하는 데는 2가지 방법이 있다.
  \1) 직접 할당 :setState(state +1)
  2)함수를 할당:setState(state => state +1) (함수의 첫번째 인자는 현재 state 이다)

  현재 state랑 관련이 없는 값을 새로운 state로 하고싶은 경우에는 (1),
  현재 state에 조금의 변화를 주어서 새로운 state를 주고 싶은 경우에는 (2)

- flip
  const onFlip = () => setFlipped(!flipped);
  -> flipped가 true라면 부정명제인 !flipped는 false
  -> false라면 true

  state값으로 input을 enabled할지 disabled 할지를 결정할 수 있음

  디폴트 값이 false 라고 정했으므로 Hours는 disabled 되어야함
  그래서 disabled={flipped === false}를 써줘서
  flipped가 false라면, disabled는 true가 되도록 만들어줌
  Minuets에는 반대로
  disabled={flipped === true}라고 써줌
  그러나
  Hours는
  disabled={!flipped}
  Minuets에는 반대로
  disabled={flipped}
  주는게 더 짧고 좋음

  시간 -> 분 컨버터
  삼항연산자(ternary operator) 사용하기
  flipped ? amount : amount / 60
  -> 만약 flipped 상태면 state에 있는 값을 그대로 보여주기
  아니라면 60으로 나눈 변환된 값 보여주기
  value={flipped ? amount * 60 : amount}
  -> 만약 flipped 상태면 60으로 곱한 변환된 값 보여주기
  아니라면 state에 있는 값을 그대로 보여주기

  flip누르면 변화된 값 그대로 가져오므로
  onFlip 변수에 reset(); 넣어주기

- 속성으로 value 를 가질 수 있으면 onChange 속성을 붙일 수 있다.
  SELECT, OPTION에도 붙힐 수 있다 (드롭다운) 11:12 참고하자

  useState의 두번째 인자인 modifier함수를 실행하면 해당 컴포넌트가 리렌더링 된다.

  [리렌더링 조건]
  \1) props이 바뀔때
  \2) state가 바뀔때
  \3) 부모 컴포넌트가 리렌더링 될 때

- 



















