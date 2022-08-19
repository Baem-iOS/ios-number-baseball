## 1. 제목: 숫자야구 게임

## 2. 소개
* 숫자야구 게임은 사용자가 입력한 수와 임의로 생성한 정수를 비교하는 게임입니다.
* 9번의 기회 안에 3 스트라이크를 얻어내면 사용자가 승리합니다.

## 3. 팀원
| baem | 준호 |
| -------- | -------- |
| <img width="160px" src="https://cdn.discordapp.com/attachments/1007898491630145587/1010091194807750716/11.png">| <img width="180px" src="https://media.discordapp.net/attachments/1007898491630145587/1010092142464614500/unknown.png">|

## 4. 타임라인: 시간 순으로 프로젝트의 주요 진행 척도를 표시
* STEP 1
    1. 임의의 세 자리 정수 생성 함수 추가
    2. 두 세자리 정수를 비교하는 함수 추가
    3. 숫자야구 게임 실행 함수 추가
* STEP 2
    1. 사용자에게서 메뉴 번호를 입력받는 함수 추가
    2. 사용자에게서 세 자리 정수를 입력받는 함수 추가
    3. 입력받은 메뉴 번호 유효성 검사하는 함수 추가
    4. 입력받은 사용자 세 자리 정수 유효성 검사하는 함수 추가
    5. 메뉴 실행 함수 추가  

## 5. 시각화된 프로젝트 구조(다이어그램 등)
<img src = "https://user-images.githubusercontent.com/77507952/185007293-69d15b81-d05e-4b90-ad40-b012bc412970.png">

## 6. 실행 화면(기능 설명)
<img src = "https://media.discordapp.net/attachments/1007898491630145587/1010086645313318992/2022-08-19_16.23.21.png?width=546&height=919">
    
* 정상적인 게임 결과 출력

## 7. 트러블 슈팅
1. 타입 선언을 명시적으로 하는 것이 좋은지, 혹은 암시적으로 하는것이 좋은지 고민.
    - 두 명이 의논하여 타입 선언을 명시적으로 하기로 정했습니다.
2. "입력이 잘못되었습니다."를 출력할 때, 메뉴가 선택 되어 잘못 입력 했을 때 출력을 해야 할 지(경우1) 오류를 처리하는 부분에서 출력을 해야 할 지(경우2) 고민
    - 하지만 같이 고민 한 결과 오류 구문이기 때문에 오류를 처리 하는 부분에서 출력하기로 결정 했습니다. 정상적인 실행을 넘어 더 적절한 위치를 찾기위해 많은 노력을 했던 것 같습니다.
~~~swift
    // 경우 1
    func receiveMenuNumber() -> Int? {
        print("1. 게임시작\n2. 게임종료\n원하는 기능을 선택해주세요 : ", terminator: "")
        if let selectedMenu = Int(readLine() ?? "") {
            return selectedMenu
        } else {
            print("입력이 잘못되었습니다.")
            return nil
        }
    }

    // 경우 2
    func choiceMenu() {
        while true {
            guard let menuNumber = receiveMenuNumber(), isCorrectMenuNumber(menuNumber) else {
                print("입력이 잘못되었습니다.")
                continue
            }
        }
    }
~~~
