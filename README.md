# 자동차 경주 게임

---

## 자동차 경주 단위테스트

### 1. String 클래스에 대한 학습 테스트

`요구사항 1`
 * [x] "1,2"을 ,로 split 했을 때 1과 2로 분리 테스트 : assertj contains()
 * [x] "1"을 ,로 split 했을 때 1만을 포함하는 배열이 반환 테스트 : assertj containsExactly()

`요구사항 2`
 * [x] "(1,2)" 값이 주어졌을 때 String substring() 활용해 "1,2"를 반환하도록 구현

`요구사항 3`
 * [x] "abc" 값이 주어졌을 때 String의 charAt() 메소드를 활용해 특정 위치의 문자를 가져온다
 * [x] 특정 문자를 위치 가져올 때 StringIndexOutOfBoundsException 발생 테스트 구현 
 * [x] AssertJ Exception Assertions 문서 참고 : import static org.assertj.core.api.Assertions.*;]
 * [x] JUnit의 @DisplayName을 활용해 테스트 메소드의 의도를 드러낸다.

---

### 2. Set Collection 학습 테스트

`요구사항`
 * [x] Set의 size() 메소드를 활용해 Set 크기 확인 테스트
 * [x] Set의 contains() 메소드를 활용 1, 2, 3의 값 존재 확인 테스트
 * [x] JUnit의 ParameterizedTest 활용 중복 코드 제거
 * [x] 입력 값에 따라 결과 값이 다른 경우 테스트 구현 @CsvSource 활용

---

### 3. 문자열 덧셈 계산기

`기능 요구사항` 
 * [x] 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환 
 * [x] (예: “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6)
 * [x] 앞의 기본 구분자(쉼표, 콜론)외에 커스텀 구분자를 지정할 수 있다. 
 * [x] 커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다. 
 * [x] 예를 들어 “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
 * [x] 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 RuntimeException 예외를 throw한다.


`AssertJ Exception Assertions` : https://www.baeldung.com/assertj-exception-assertion

---
### 자동차 경주

`기능 요구사항`
- 초간단 자동차 경주 게임을 구현한다.
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 사용자는 몇 대의 자동차로 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4이상일 경우이다.
- 자동차의 상태를 화면에 출력한다. 어느 시점에 출력할 것인지에 대한 제약은 없다.

`기능 요구사항 정리 List`
- [x] 자동차 개수 와 이동 횟수 입력 기능
- [x] UI InputView 출력
- [x] UI ResultView 출력
- [x] 랜덤 난수 생성 기능 : 0~9
- [x] 랜덤 난수 생성 결과 판단 기능
  - 0~3 : false 멈춤
  - 4~9 : ture 전진
- [x] 자동차 이동 기능 : 랜덤 난수 생성 결과 true 리턴할 경우