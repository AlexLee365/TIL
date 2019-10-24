# RxSwift

개념 : Swift에서 쓰이는 리액티브 프로그래밍 방식의 라이브러리

<br/>

### # Observable

**: observer가 구독할 수 있는 객체**
=> Observable이 배출하는 하나 or 연속된 항목에 반응



#### **## <u>Subscribe 메서드</u>를 통해 observer <=> observable 을 연결한다.**

1.  onNext 
(usually called "emissions" of items)
   Observable이 새로운 항목들을 배출할때마다 이 메서드를 호출하여, 배출항목을 파라미터로 전달 받음

2. onError
기대하는 데이터가 생성되지않음 or 다른 오류 발생 => 오류를 알리기 위해 이 메소드 호출
   => 오류정보를 저장하고 있는 객체를 파라미터로 전달 받음
<u>** 이 메소드가 호출되면 onNext, onCompleted 는 더이상 호출되지 않음!</u>
   
3. onCompleted
마지막 onNext 호출 이후 이 메소드 호출 (오류가 발생하지 않았을 시)



#### ## Unsubscribing









출처
http://reactivex.io/documentation/observable.html



<br/>

### # Operator

(ReactiveX: Reactive Extensions 리액티브 확장을 강력하게 해주는 요소)

**배출하는 연속된 항목들을 변환, 결합, 조작함**



#### ## Observable 생성

: 새로운 Observable을 생성, 시작

- Create

  

- Defer

- Empty / Never / Throw
Empty
  항목이 없지만 정상적으로 종료되는 Observable 반환 => return Void 같은 느낌
ex. Driver.empty(), Observable.empty()
  

  
- From
여러 객체, 데이터들을 차례대로 방출하는 Observable 생성
  
- Interval

- Just
들어온 값을 그대로 방출하는 Observable 생성
  
- Range

- Repeat

- Start

- Timer



#### ## Observable 변환

: Observable이 생성한 항목을 변환

- Buffer
- FlatMap
- Map
- GroubBy
- Scan
- Window



#### ## Observable 필터링

: Observable이 생성한 항목들 중에서 선택적으로 방출

- Debounce
- Distinct
- ElementAt
- Filter
- First
- IgnoreElements
- Last
- Sample
- Skip
- SkipLast
- Take
- TakeLast



#### ## Observable 결합

: 여러 Observable을 결합하여 단일 Observable을 생성

- And / Then / When

- CombineLatest
여러개의 Observable을 묶는데, 그 중 하나가 이벤트가 발생하더라도 그 새로운 이벤트로 갱신하여 새로운 데이터 반환
  
- Join

- Merge
여러개의 Observable을 결합 (Observable의 타입들이 모두 같아야함)
  
- StartWith

- Switch

- Zip



#### ## Error Handling 오류 처리

: Observable에서 오류 알림을 복구

- Catch
- Retry



#### ##



<br/>

### # Subject









