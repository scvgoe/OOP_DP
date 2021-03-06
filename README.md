# 개발자가 반드시 정복해야 할 객체지향과 디자인 패턴 - 최범균 지음 (인투북스)

## Chapter 01 들어가기

### 1. 지저분해지는 코드
### 2. 수정하기 좋은 구조를 가진 코드
### 3. 소프트웨어의 가치

## Chapter 02 객체 지향

### 1. 절차 지향과 객체 지향

#### 1.1 절차 지향

소프트웨어를 구현한다는 것은 결국 소프트웨어를 구성하는 데이터와 데이터를
조작하는 코드를 작성하는 것. 이렇게 데이터를 조작하는 코드를 프로시져나 함수의
형태로 분리하여, 프로시져로 프로그램을 구성하는 기법을 절차 지향 (Procedural
Oriented) 프로그래밍이라 한다.
   ​

* 절차 지향이라는 말 때문에 뭔가 순서에 따라 프로그래밍하는 방식을 생각할 수
  있으나 단순히 프로시져라는 말을 번역하면서 생겨난 말
  
다수의 프로시저들이 데이터를 공유하는 방식으로 만들어지기 때문에, 절차 지향
프로그램은 자연스럽게 데이터를 중심으로 구현하게 된다.

최초에는 절차 지향적으로 코드를 구현하기 쉽지만 프로그램의 규모가 커져서 데이터
종류가 증가하고 이를 사용하는 프로시져 또한 증가하면 다음의 문제들이 발생할 수
있다.


* 데이터 타입이나 의미를 변경해야 할 때, 함께 수정해야 하는 프로시저가 증가
* 같은 데이터를 프로시저들이 서로 다른 의미로 사용하는 경우가 발생

#### 1.2 객체 지향

데이터와 관련된 프로시져를 객체라는 단위로 묶는다.
프로그램의 규모가 작을 때에는 절차 지향보다 더 복잡한 구조를 갖게 된다.


### 2. 객체

#### 2.1 객체의 핵심은 기능을 제공하는 것

#### 2.2 인터페이스와 클래스

객체가 제공하는 기능을 오퍼레이션(operation)이라고 부른다.
오퍼레이션의 사용법은 아래의 세 가지로 구분되며, 이를 합쳐 시그니처
(signature)라고 부른다.  ​

- 기능 식별 이름

- 파라미터 및 파라미터 타입

- 기능 실행 결과 값

객체가 제공하는 모든 오퍼레이션 집합을 객체의 인터페이스(interface)라고 부르며
서로 다른 인터페이스를 구분할 때 사용되는 명칭이 바로 타입(type)이다.


- 여기서 말하는 인터페이스는 자바 언어나 C# 언어에 포함되어 있는 인터페이스가 아니라, 객체 지향에서 오퍼레이션 집합을 표현할 때 사용되는 용어

인터페이스는 객체가 제공하는 기능에 대한 명세서일 뿐, 실제 객체가 기능을 어떻게
구현하는지에 대한 내용은 포함하고 있지 않다. 실제 객체의 구현을 정의하는 것은
클래스(class)이다.

#### 2.3 메시지

어떤 객체에 오퍼레이션의 실행을 요청하는 것을 '메시지를 보낸다'라고 표현한다.
자바와 같은 언어에서 메서드를 호출하는 것이 메시지를 보내는 과정에 해당한다.  ​

### 3. 객체의 책임과 크기

객체가 갖는 책임을 결정하는 것이 객체 지향 설계의 출발점이다. 프로그램을
작성하기에 앞서 프로그램이 필요로 하는 기능들의 목록을 작성해야 한다. 이
기능들을 객체들에게 어떻게 분배하느냐에 따라 객체의 구성이 달라진다. 모든
상황에 들어맞는 객체-책임 구성 규칙이 존재하는 것은 아니지만, 한 가지 확실한
규칙은 객체가 갖는 책임의 크기는 작을수록 좋다는 것이다. 즉, 객체가 제공하는
기능의 개수가 작아야 한다는 것을 의미한다.

* 한 객체에 기능이 많아지면 절차 지향적인 구조를 갖게 된다.

객체가 갖는 책임의 크기가 작아질수록 객체 지향의 장점인 변경의 유연함을 얻을 수
있다. 객체의 크기와 관련된 원칙이 있는데 바로 단일 책임 원칙(Single
Responsibility Principle: SRP)이다.

단일 책임 원칙에 대한 내용은 '5장 설계원칙: SOLID' 에서 자세히 살펴본다.

* 객체의 역할 = 객체의 책임

  ​

### 4. 의존
한 객체가 다른 객체를 이용하여 완성된다면, 이는 의존 관계에 있다고 말할 수
있다. 변경은 의존 관계를 따라 전이되기 때문에, (A <- B <- C <- A) 와 같은 순환
의존이 발생하지 않도록 의존 역전 원칙 (Dependency inversion principle: DIP)를
잘 지킬 수 있어야 한다.

#### 4.1 의존의 양면성
- 내가 변경되면 나에게 의존하고 있는 코드에 영향을 준다.
- 나의 요구가 변경되면 내가 의존하고 있는 타입에 영향을 준다.



### 5. 캡슐화

캡슐화(encapsulation)은 객체가 내부적으로 기능을 어떻게 구현하는지를 감추는
것이다.

#### 5.1 절차 지향 방식 코드

#### 5.2 캡슐화 된 기능 구현
캡슐화는 변경의 여파를 최소화한다.

#### 5.3 캡슐화의 결과는 내부 구현 변경의 유연성 획득

#### 5.4 캡슐화를 위한 두 개의 규칙

- Tell, Don't Ask
	
	데이터를 읽는 것은 데이터를 중심으로 코드를 작성하게 만드는 원인이 되므로, 
	데이터 대신에 기능을 실행해달라고 명령을 내려야 한다.

- 데미테르의 법칙(Law of Demeter)
	
	앞선 'Tell, Don't Ask' 규칙을 따를 수 있도록 만들어 주는 또 다른 규칙으로 다음의
	간단한 규칙으로 구성된다.
	- 메서드에서 생성한 객체의 메서드만 호출
	- 파라미터로 받은 객체의 메서드만 호출
	- 필드로 참조하는 객체의 메서드만 호출

*   신문 배달부와 지갑 예시 참조
*   데미테르의 법칙을 디키지 않는 전형적인 증상 두 가지
    * 연속된 get 메서드 호출
    * 임시 변수의 get 호출이 많음

      ​

### 6. 객체 지향 설계 과정
- 제공해야 할 기능을 찾고 또는 세분화하고, 그 기능을 알맞은 객체에 할당한다.
    - 기능을 구현하는데 필요한 데이터를 객체에 추가한다. 객체에 데이터를 먼저
      추가하고 그 데이터를 이용하는 기능을 넣을 수도 있다.
    - 기능은 최대한 캡슐화해서 구현한다.
- 객체 간에 어떻게 메시지를 주고받을 지 결정한다.
- 개발하는 동안 지속적으로 앞선 두 과정을 반복한다.

## Chapter 03 다형성과 추상 타입

### 1. 상속 개요

### 2. 다형성과 상속
다형성(polymorphism)은 한 객체가 여러 가지 모습을 갖는다는 것을 의미한다.
여기서 모습이란 타입을 뜻하는데, 즉 다형성이란 한 객체가 여러 타입을
가질 수 있다는 것을 의미한다.

#### 2.1 인터페이스 상속과 구현 상속

인터페이스 상속은 정의만 상속하는 것을 말하고, 구현 상속은 상위 클래스의
구현도 상속받는 것을 의미한다.


### 3. 추상 타입과 유연함
추상화(abstraction) 데이터나 프로세스 등을 의미가 비슷한 개념이나 표현으로
정의하는 과정이다.

[무의미해 보이는 데이터, 프로세스 등을 유의미하게 정의하는 것]

#### 3.1 추상 타입과 실제 구현의 연결

추상 타입과 실제 구현 클래스는 상속을 통해서 연결한다.
상속 받은 인터페이스(ex. java)를 구현하는 클래스들을 concrete class라고 부른다.

* [추상화가 추상 타입과 실제 구현의 연결로만 이루어지는 것은 아님!]



#### 	3.2 추상 타입을 이용한 구현 교체의 유연함

* 예시 중요



#### 	3.3 변화되는 부분을 추상화하기
변화 요구가 있었던 부분은 앞으로도 변화 요구가 있을 확률이 높으므로 변화되는
부분을 추상화 한다.

#### 	3.4 인터페이스에 대고 프로그래밍하기 (program to interface)
[java나 C#의 interface가 아니다]

#### 	3.5 인터페이스는 인터페이스 사용자 입장에서 만들기

#### 	3.6 인터페이스와 테스트
인터페이스를 사용하면 Mock 객체를 활용하여 테스트를 수월하게 진행할 수 있다.

* TDD (Test Driven Development) - 객체 지향 설계를 유도하는 좋은 개발 방식


## Chapter 4 재사용: 상속보단 조립

### 1. 상속과 재사용

상속을 통해 재사용을 쉽게 할 수 있는 것은 분명하다. 하지만 상속은 변경의
유연함이라는 측면에서 치명적인 단점을 갖는다.

#### 1.1 상속을 통한 재사용의 단점 1. 상위 클래스 변경의 어려움

하위 클래스는 상위 클래스에 의존하고 있기 때문에, 상위 클래스를 변경하게 되면
당연히 하위 클래스도 이에 영향을 받게 된다.
따라서 클래스 계층도가 커질수록 상위 클래스를 변경하는 것은 점점 어려워진다.

#### 1.2 상속을 통한 재사용의 단점 2. 클래스의 불필요한 증가

매 새로운 기능이 추가될 때마다 관련된 클래스가 있음에도 새로 구현해야 하는
경우가 생긴다.

                        Storage

    CompressedStorage   EncryptedStorage    CacheableStorage

    CompressedEncrypted EncryptedCompressed CacheableEncrypted
    Storage             Storage             Storage



#### 	1.3 상속을 통한 재사용의 단점 3. 상속의 요용

​B라는 객체가 A라는 객체를 상속받아 put이라는 메서드를 구현하려고 한다고 하자.
​이 때 객체 A에 add라는 메서드가 이미 존재했고, 추후에 B 객체를 사용하는
​개발자들이 put과 add를 혼용하여 사용할 수 있는 오용의 여지가 발생한다.

[예시 참조]

* 상속은 IS-A 관계가 성립할 경우에만 사용해야 한다 [B is a A]


### 2. 조립을 이용한 재사용

객체 지향 언어에서 객체 조립은 보통 필드에서 다른 객체를 참조하는 방식으로
구현된다.

* 모든 상황에서 객체 조립을 사용하라는 것은 아니지만 상속을 사용하면 변경의
유연함이 떨어질 가능성이 높으니 객체 조립을 먼저 고려할 것

#### 2.1 위임

위임(delegation)은 내가 할 일을 다른 객체에게 넘긴다는 의미를 담고 있으며, 보통
조립 방식을 이용해서 위임을 구현한다.

* 위임을 사용하면 호출이 증가하기 때문에, 실행 시간은 증가하므로 연산 속도가
매우 중요한 시스템에서는 많은 위임 코드가 성능에 문제를 일으킬 수 있음.

#### 2.2 상속은 언제 사용하나?

상속을 사용할 때에는, 재사용이라는 관점이 아닌 기능의 확장이라는 관점에서
상속을 적용해야 하고 명확한 IS-A 관계가 성립되어야 한다.


## Chapter 05 설계 원칙: SOLID

- 단일 책임 원칙 (Single responsibility principle; SRP)
- 개방-폐쇄 원칙 (Open-closed principle; OCP)
- 리스코프 치환 원칙 (Liskov substitution principle; LSP)
- 인터페이스 분리 원칙 (Interface segregation principle; ISP)
- 의존 역전 원칙 (Dependency inversion principle; DIP)



### 1. 단일 책임 원칙 (Single responsibility principle)
- 클래스는 단 한 개의 책임을 가져야 한다.

  * 클래스를 변경하는 이유는 단 한 개여야 한다.


#### 1.1 단일 책임 원칙 위반이 불러오는 문제점

[변화의 유연성 부족]

  ​

#### 1.2 책임이란 변화에 대한 것

단일 책임 원칙을 잘 지키기 위해서는 메서드를 실행하는 것이 누구인지 확인해 보면
된다. 클래스의 사용자(사람이 아니라 클래스)들이 서로 다른 메서드들을 사용한다면
그들 메서드는 각각 다른 책임에 속할 가능성이 높고, 책임 분리 후보가 될 수 있다.


#### 2. 개방 폐쇄 원칙 (Open-closed principle)
- 확장에는 열려 있어야 하고, 변경에는 닫혀 있어야 한다.
    - 기능을 변경하거나 확장할 수 있으면서
    - 그 기능을 사용하는 코드는 수정하지 않는다.

확장되는 부분(즉, 변화되는 부분)을 추상화해서 표현함으로 개방 폐쇄 원칙을
구현할 수 있다. 상속을 통해서도 개방 폐쇄 원칙을 구현할 수 있다. 상속되는
클래스의 메서드를 오버라이드 하면 된다. 클래스 B가 A를 상속받아서 구현이 됐다면
A의 기능을 확장하면서도 이와 동시에 B는 수정하지 않으므로 확장에는 열려
있으면서 변경에는 닫혀 있다고 말할 수 있는 것이다.


#### 	2.1 개방 폐쇄 원칙이 깨질 때의 주요 증상

- 다운 캐스팅을 한다. [하위 클래스로 타입을 캐스팅하는 것]

  instanceof와 같은 타입 확인 연산자가 사용된다면 해당 코드는 개방 폐쇄 원칙을
  지키지 않을 가능성이 높다.

- 비슷한 if-else 블록이 존재한다.
  [예시 참조]



#### 	2.2 개방 폐쇄 원칙은 유연함에 대한 것

​개방 폐쇄 원칙은 변화되는 부분을 추상화함으로써 사용자[사람X] 입장에서 변화를
​고정시킨다. 상속을 통한 개방 폐쇄 원칙 구현에서도 변화되는 부분을 하위
​클래스에서 오버라이딩 함으로써 기존 기능을 확장시킬 수 있었고, 하위 클래스에서
​변경하더라도 상위 클래스는 변경할 필요가 없는 구조를 만들 수 있었다.


### 3. 리스코프 치환 원칙 (Liskov substitution principle)

리스코프 치환 원칙은 개방폐쇄 원칙을 받쳐 주는 다형성에 관한 원칙을 제공한다.

- 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는
  프로그램은 정상적으로 동작해야 한다. [예시 참조]

  ​

#### 3.1 리스코프 치환 원칙을 지키지 않을 때의 문제

직사각형-정사각형 문제 [예시 참조]
개념적으로 상속 관계에 있는 걱처럼 보일지라도 실제 구현에서는 상속 관계가 아닐
수도 있다.

상위 타입에서 지정한 리턴 값의 범위에 해당되지 않는 값을 리턴하는 것도 또 다른
문제가 될 수 있다. [예시 참조]



#### 	3.2 리스코프 치환 원칙은 계약과 확장에 대한 것

​기능 실행의 계약과 관련해서 흔히 발생하는 위반 사례로는 다음과 같은 것들이
​있다.

- 명시된 명세에서 벗어난 값을 리턴한다.

- 명시된 명세에서 벗어난 익셉션을 발생한다.

- 명시된 명세에서 벗어난 기능을 수행한다.

명세에 기반해서 구현한 코드는, 하위 타입이 상위 타입에서 정의한 명세를 벗어나지
앟는 범위에서 구현해야 한다.

타입을 확인하는 기능을 사용하는 것은 전형적인 리스코프 치환 원칙을 위반할 대
발생하는 증상. 클라이언트가 instanceof 연산자를 사용한다는 것은 상위 타입만을
사용해서 프로그래밍 할 수 없다는 것을 뜻하며, 이는 하위 타입이 상위 타입을
대체할 수 없다는 것을 의미한다. 이는 새로운 종류의 하위 타입이 생길 때마다 상위
타입을 사용하는 코드를 수정해줘야 할 가능성을 높이게 되고, 결국 개방 폐쇄
원칙을 지킬 수 없도록 만든다.

### 4. 인터페이스 분리 원칙(Interface segregation principle)
- 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.

#### 	4.1 인터페이스 변경과 그 영향

​여러 가지 UI 기능을 구현한 각 .cpp 파일들은 각 함수의 명세가 포함된 .h 파일에
​의존하게 되는데 이 경우 C.cpp에서 사용하는 함수의 시그니쳐가 변경될 경우에 I.h
​C.cpp를 수정하게 된다. 하지만 이와 관련이 없는 A.cpp B.cpp도 다시 컴파일을
​해주어야 하는 문제가 발생한다.

​A.cpp B.cpp C.cpp
 	   (의존)
  	    I.h

#### 	4.2 인터페이스 분리 원칙

​위의 예시에서 I.h는 A.h B.h C.h로 분리를 해서 구현하는 것이 인터페이스 분리
​원칙을 지켰다고 말할 수 있다.

​위의 문제들이 꼭 컴파일과 관련한 문제만은 아니다 용도에 맞게 인터페이스를
​분리하는 것은 단일 책임 원칙과도 연결된다. 또 단일 책임 원칙이 잘 지켜지면
​인터페이스와 콘크리트 클래스의 재사용 가능성을 높일 수 있다.

#### 	4.3 인터페이스 분리 원칙은 클라이언트에 대한 것

### 5. 의존 역전 원칙(Dependency inversion principle)
- 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안 된다. 저수준 모듈이 고수준
  모듈에서 정의한 추상 타입에 의존해야 한다.

		[예시]
		
		고수준 모듈
		바이트 데이터를 읽어와 암호화 하고 결과 데이터를 쓴다.

		저수준 모듈
		파일에서 바이트 데이터를 읽어온다.
		AES 알고리즘으로 암호화한다.
		파일에 바이트 데이터를 쓴다.

#### 	5.1 고수준 모듈이 저수준 모듈에 의존할 때의 문제

​[예시 참조]

​우리가 원하는 것은 저수준 모듈이 변경되더라도 고수준 모듈은 변경되지 않는
​것인데, 이를 위한 원칙이 바로 의존 역전 원칙이다.



#### 	5.2 의존 역전 원칙을 통한 변경의 유연함 확보

​의존 역전 원칙은 이런 문제를 저수준 모듈이 고수준 모듈을 의존하게 만들어서
​해결한다. 고수준 모듈에서 저수준 모듈을 사용한다는 것은 고수준 모듈이 저수준
​모듈에 의존한다는 의미인데, 어떻게 반대의 경우를 만든다는 걸까? 답은 추상화에
​있다. 저수준 모듈을 추상화하는 것이다.

#### 	5.3 소스 코드 의존과 런타임 의존

​추상화 된 저수준 모듈은 고수준 모듈의 입장에서 만들어지는데, 이것은 고수준
​모듈이 저수준 모듈에 의존했던 상황이 역전되어 저수준 모듈이 고수준 모듈에
​의존하게 된다는 것을 의미한다.

​[예시 참조]

* 의존 역전 원칙은 런타임의 의존이 아닌 소스 코드의 의존을 역전시킴으로써
​변경의 유연함을 확보할 수 있도록 만들어 주는 원칙이지, 런타임에서의 의존을
​역전시키는 것은 아니다.

#### 	5.4 의존 역전 원칙과 패키지

​의존 역전 원칙은 타입의 소유도 역전시키는데, 이는 각 패키지를 독립적으로 배포할
​수 있도록 만들어 준다. 따라서 불필요한 모듈이 포함되는 것을 방지할 수 있다.

### 6. SOLID 정리

SOLID 원칙을 한 마디로 정의하면 변화에 유연하게 대처할 수 있는 설계 원칙이다.
	
단일 책임 원칙과 인터페이스 분리 원칙은 객체가 커지지 않도록 막아 준다. 객체가
많은 기능을 가지게 되면, 객체가 가진 기능의 변경 여파가 그 객체의 다른
기능에까지 번지게 되고 이는 다시 다른 기능을 사용하는 클라이언트에게까지 영향을
준다. 객체가 단일 책임을 갖게 하고 클라이언트마다 다른 인터페이스를 사용하게
함으로써 한 기능의 변경이 다른 곳에까지 미치는 영향을 최소화할 수 있고, 이는
결국 기능 변경을 보다 쉽게 할 수 있도록 만들어 준다.
	
리스코프 치환 원칙과 의존 역전 원칙은 개방 폐쇄 원칙을 지원한다. 개방 폐쇄
원칙은 변화되는 부분을 추상화하고 다형성을 이용함으로써 기능 확장을 하면서도
기좆 코드를 수정하지 않도록 만들어 준다. 여기서, 변화되는 부분을 추상화할 수
있도록 도와주는 원칙이 바로 의존 역전 원칙이고, 다형성을 도와주는 원칙이
리스코프 치환 원칙인 것이다.
	
또한, SOLID 원칙은 사용자 입장에서의 기능 사용을 중시한다. 인터페이스 분리
원칙은 클라이언트 입장에서 인터페이스를 분리하고 있으며, 의존 역전 원칙 역시
저수준 모듈을 사용하는 고수준 모듈 입장에서 추상화 타입을 도출하도록 유도한다.
또한, 리스코프 치환 원칙은 사용자에게 기능 명세를 제공하고, 그 명세에 따라
기능을 구현할 것을 약속한다. 이처럼 SOLID 원칙은 사용자 관점에서의 설계를
지향하고 있다.

   ​