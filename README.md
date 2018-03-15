#Basic API
---------------
API는 라이브러리라고 부르기도 하는데, 프로그램 개발에 가주 사용되는 클래스 및 인터페이스의 모음을 말한다. 

##API Document
--------------------

API 도큐먼트는 세개의 프레임으로 나뉘어져 있다. 

좌측 상단 프레임 : 패키지 전체 목록

좌측 하단 프레임 : 패키지에 속하는 클래스와 인터페이스 목록

중앙 프레임 : 좌측 하단 프레임에서 선택한 클래스나 인터페이스에 대한 상세 설명

**중앙 프레임 내용 구성**

상단 부분 (중앙 프레임) : 클래스가 포함된 패키지 정보. 상속 정보, 인터페이스 구현 정보

중앙 부분 (중앙 프레임) : 클래스의 설명과 사용 방법

하단 부분 (필드, 생성자, 매소드 목록

##java.lang / java.util
--------------------
**java.lang**

공통적으로 가장 많이 사용하는 패키지

: Object, System, class, String, StringButter, StringBuilder, Math, Wrapper


**java.util**

: Array, Calender, Date,Object, StringTokenizer, Random

##Object Class
-------------------

클래스를 선언할 때 extends 키워드로 다른 클래스를 상속하지 않으면 암시적으로 java.lang.Object 클래스를 상속한다. 모든 자바 클래스는 Object의 자식이거나 자손 클래스이다. 

##equals() (객체비교)
--------------------
Object 클래스의 equals() 메소드는 비교연산자인 ==과 동일한 결과를 리턴한다. 
두 객체가 동일한 객체라면 true를 리턴하고 그렇지 않으면 false를 리턴한다.


```
public class MemberExample{
	public static void main(String[] args){
		Member obj1 = new Member("blue");
		Member obj2 = new Member("blue");
		Menber obj3 = new Member("red");
		
		if(obj1.equals(obj2){
			System.out.println("동일하다")
		}else{
			System.out.println("동일하지않다")
		}
		
		if(obj1.equals(obj3){
			System.out.println("동일하다")
		}else{
			System.out.println("동일하지않다")
		}
	}
	
	// 결과 : obj1과 obj2는 동일하다.
	//		  obj1과 obj3는 동일하지 않다. 
	
```
	


	
##hashCode() (객체 해쉬코드)
-----------------

 객체 해시코드란 객체를 식별할 하나의 정수 값을 말한다. Objectd의 hashCode() 메소드는 객체의 메모리 번지를 이용해서 해시 코드를 만들어 리턴하기 때문에 객체마다 다른 값을 가지고 있다. 
 
해시코드 값이 다르면 다른 객체로 판단하고 해시코드 값이 같으면 equals() 메소드로 다시 비교한다. 그렇기 때문에 hashCode() 메소드가 true가 나와도 equals()의 리턴 값이 다르면 다른 객체가 된다. 



##toString() (객체 문자 정보)
-----------------------
Object 클래스의 toString()메소드는 객체의 문자 정보를 리턴한다. 

객체의 문자 정보란 객체를 문자열로 표현한 값을 말한다. 

**Object 하위 클래스는 toString() 메소드를 재정의(오버라이딩)하여 간결하고 유익한 정보를 리턴하도록 되어있다.**

```
//예시 toString 재정의

public class SmartPhone{
	private String company;
	private String os;
	
	public SmartPhone(String company, String os){
		this.company = company;
		this.os = os;
	}
	
	//toString 재정의
	@Override
	public String toString(){
		return company+","+os;
	}
}
```


##Wapper Class
----------

자바는 기본 타입의 값을 갖는 개체를 생성할 수 있다. 이런 객체를 Wrapper 객체라고 하는데, 그 이유는 기본 타입의 값을 내부에 두로 포장하기 때문이다. 
**포장 객체의 특징은 포장하고 있는 기본 타입 값은 외부에서 변경할 수 없다. 만약 내부의 값을 변경하고 싶다면 새로운 포장 객체를 만들어야한다**



##Boxing(박싱) / Unboxing(언박싱)
--------------
Boxing : 기본 타입의 값을 포장 객체로 만드는 과정

Unboxing : 포장 객체에서 기본 타입의 값을 얻어내는 과정

```
// 예시
// 기본 타입의 값을 박싱하고 언박싱하기

public class BoxingUnBoxingExample{
	public static void main(String[] args){
		//Boxing
		Integer obj1 = new Integer(100);
		Integer obj2 = new Integer("200");
		Integer obj3 = new Integer.valueOf("300");
		
		
		//Unboxing
		int value1 = obj.intvalue();
		int value2 = obj2.intvalue();
		int value3 = obj3.intvalue();
	}
}
```



		
			
