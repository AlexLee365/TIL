# Cocoapods 이슈



##### CocoaPods could not find compatible versions for pod "Something"

![스크린샷 2019-10-23 오후 4.12.15](/Users/alelee_dev/Desktop/TIL/assets/스크린샷 2019-10-23 오후 4.12.15.png)

: 코코아팟 라이브러리 목록들에 대해 해당 버전을 뭘깔아야하는지 로컬에 정보를 저장해놓는데, 그 정보랑 지금 필요한 라이브러리 버전 정보랑 일치하지않아서 생기는 문제?

=> 'pod repo udpate' 를 통해 로컬에 저장된 정보를 한번 업데이트 해줘야함

