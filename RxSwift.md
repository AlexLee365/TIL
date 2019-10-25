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
   **이 메소드가 호출되면 onNext, onCompleted 는 더이상 호출되지 않음!**

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
  : 항목이 없지만 정상적으로 종료되는 Observable 반환 => return Void 같은 느낌  
    ex. `Driver.empty()`, `Observable.empty()`
  
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

: 데이터를 전달받아 Subscriber들에게 뿌려주는 역할

#### ## PublishSubject

<img width="500" alt="S PublishSubject" src="https://user-images.githubusercontent.com/47735434/67456236-02c66200-f66b-11e9-9863-c4ef9969ff9c.png">

=> 이 PublishSubject를 Subscribe하고 있는 Observable들에게 **`Subscribe한 시점 이후로 생긴 아이템`**들만 방출함

** PublishSubject가 에러로 종료되면 그 구독자 Observable들에게 항목을 방출하지않고, 오류알림을 전달



#### ## BehaviorSubject

<img width="500" alt="S BehaviorSubject" src="https://user-images.githubusercontent.com/47735434/67456500-ec6cd600-f66b-11e9-981e-6019d062f5f8.png">

=> PublishSubject와 유사함. But. **`Subscribe한 시점에 BehaviorSubject의 가장 마지막 아이템`**을 가져옴.
(BehaviorSubject가 하나이상의 아이템을 가지고있어야하기때문에 생성 시 초기값 필요)

** 에러로 종료될시 PublishSubject 과정과 동일



#### ## ReplaySubject

<img width="500" alt="S ReplaySubject" src="https://user-images.githubusercontent.com/47735434/67538794-1cbf7d80-f71b-11e9-8d91-699360104b59.png">

=> 특정 크기만큼의 최신 이벤트를 캐싱하고 있다가 Subscriber에게 한번에 방출함.



출처  
https://rhammer.tistory.com/289



#### ## AsyncSubject

<img width="500" alt="S AsyncSubject" src="https://user-images.githubusercontent.com/47735434/67460636-7883fb00-f676-11e9-8981-6c9620db4239.png">

=> 아이템들 중 **`마지막 아이템 (Complete 됬을 때 발생)`**을 Subscriber하고 있는 Observable들에게 방출



#### ## Variable







### # Relay