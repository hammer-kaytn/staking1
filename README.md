# 인터페이스
극단적으로 동일한 목적 하에 동일한 기능을 수행하게끔 강제하는 것이 바로 인터페이스의 역할이자 개념이다. 조금 더 유식하게 말하면, 자바의 다형성을 극대화하여 개발코드 수정을 줄이고 프로그램 유지보수성을 높이기 위해 인터페이스를 사용한다.
- 개발자 사이의 코드 규약을 정한다.
- 여러 구현체에서 공통적인 부분을 추상화한다.(다형성)

이건 개인적인 생각이지만 이런 인터페이스(규칙)을 정함으로서 이더리움의 ERC-20이 빠른속도로 발전할수 있는 가장 기본적인 기반이지 않았을까 생각한다.
즉 규칙을 정함으로써 엄청나게 많은 개선안(EIP) 들이 나오고 서로 쉽게 호환이 될수도 있었단 생각이 든다.
# 오버라이딩
Override는 '기각하다', '무시하다'의 뜻을 담고있다. 즉, '기존의 것을 무시하고 덮어쓰다.'의 의미를 가진다. 자바에서 메소드 오버라이딩이란, 상속의 관계에 있는 클래스 간에 하위 클래스가 상위 클래스와 '완전 동일한 메소드'를 덮어쓴다는 의미이다. 여기서 '완전 동일한 메소드'라는 말은 이름과 반환형이 같으면서 매개변수의 개수와 타입까지 모두 같은 메소드라는 의미이다. 즉, 오버로딩(overload)되지 않는 (JVM이 단순히 다른 메소드라고 구별을 할 수 없는) 메소드이다.

즉 솔리디티 스마트 컨트랙트에서는 부모클레스의 기능을 자식클레스가 재정의해서 사용할수있다. 이때 재정의를 하려면 인터페이스를 규칙을 따라야한다.
- 메소드의 이름을 변경하면 안된다.
- 메소드의 매개변수의 갯수(arg1,arg2,...)와 데이터 타입(address,string,int...), 그리고 타입의 순서이다.
- 메소드의 리턴 타입 (솔리디티에서는 function () returns (타입)을 끝에 정의하는데 이걸 바꾸면 안된다.)

# Solidity 접근제어자
- private: 컨트랙트 내부에서만 접근이 가능하다.
- internal: 컨트랙트 내부 및 상속한 컨트랙트에서 접근이 가능하다. 그 외의 외부에서는 접근할 수 없다.
- public: 컨트랙트 내부 및 상속한 컨트랙트에서 접근할 수 있고, 외부에서도 접근이 가능하다.
- external: 외부에서만 접근이 가능하다.